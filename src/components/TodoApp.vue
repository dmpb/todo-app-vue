<template>
    <div class="relative h-full pb-32">
        <div class="p-4 bg-slate-50">
            <div class="container relative max-w-lg mx-auto">
                <h1 class="text-3xl font-bold text-left text-blue-600">Todo App</h1>
            </div>
        </div>
        <div class="container relative max-w-lg pt-6 mx-auto">
            <div class="p-4 rounded-md shadow-md shadow-slate-200">
                <div class="flex justify-between mb-2" v-for="(todo) in sortTodos" :key="todo.id">
                    <div class="flex">
                        <div class="flex-auto">
                            <input
                                type="checkbox"
                                :id="'todo-' + todo.id"
                                class="mr-4"
                                :checked="todo.completed"
                                @click="updateTodo(todo, todo.title, !todo.completed)"
                            />
                        </div>
                        <label
                            :for="'todo-' + todo.id"
                            :class="{ 'line-through': todo.completed }"
                        >{{ todo.title }}</label>
                    </div>
                    <button class="ml-4" @click="deleteTodo(todo)">
                        <svg
                            width="18px"
                            height="18px"
                            viewBox="0 0 24 24"
                            fill="none"
                            xmlns="http://www.w3.org/2000/svg"
                        >
                            <g id="Iconly/Curved/Delete">
                                <g id="Delete">
                                    <path
                                        id="Stroke 1"
                                        d="M18.8892 9.5542C18.8892 17.5732 20.0435 21.198 12.2797 21.198C4.5149 21.198 5.693 17.5732 5.693 9.5542"
                                        stroke="#130F26"
                                        stroke-width="1.5"
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                    />
                                    <path
                                        id="Stroke 3"
                                        d="M20.3651 6.47985H4.2146"
                                        stroke="#130F26"
                                        stroke-width="1.5"
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                    />
                                    <path
                                        id="Stroke 5"
                                        d="M15.7148 6.47983C15.7148 6.47983 16.2434 2.71411 12.2891 2.71411C8.33578 2.71411 8.86435 6.47983 8.86435 6.47983"
                                        stroke="#130F26"
                                        stroke-width="1.5"
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                    />
                                </g>
                            </g>
                        </svg>
                    </button>
                </div>
            </div>
        </div>
        <div class="fixed bottom-0 w-full p-4 bg-white border-t border-gray-200">
            <div>
                <button class="font-bold text-blue-600" @click="toggleModal()">+ Nuevo Recordatorio</button>
            </div>
        </div>
    </div>
    <div v-show="showModalTodo" class="fixed top-0 w-full h-full overflow-hidden">
        <div class="relative flex justify-center w-full h-full">
            <div class="container relative z-20 max-w-xl mt-20 h-min">
                <form @submit.prevent="addTodo()">
                    <input
                        v-model="form.title"
                        ref="title"
                        type="text"
                        placeholder="Escribe un nuevo recordatorio..."
                        class="text-2xl shadow-[0px_20px_55px_-5px_rgba(0,0,0,0.3)] placeholder-zinc-400 h-14 bg-neutral-200 w-full rounded-xl shadow-neutral-500 border-neutral-300 focus:ring-0 focus:border-neutral-300"
                    />
                </form>
            </div>
            <div @click="toggleModal()" class="absolute top-0 z-10 w-full h-full"></div>
        </div>
    </div>
</template>
<script>
import axios from "axios";

export default {
    data() {
        return {
            todos: [],
            showModalTodo: false,
            form: {
                title: null
            },
        }
    },

    mounted() {
        axios.get('https://jsonplaceholder-v1.herokuapp.com/api/todos')
            .then((result) => {
                this.todos = result.data.data
            }).catch((err) => {
                console.error(error);
            });
    },

    computed: {
        sortTodos() {
            return this.todos.sort((a, b) => {
                if (a.completed == true && b.completed == false) {

                    return 1
                }
                if (a.completed == false && b.completed == true) {
                    return -1
                }
                return 0
            })
        },
    },

    methods: {
        updateTodo(todo, title, completed) {
            const index = this.todos.findIndex(e => e.id == todo.id)

            axios.put('https://jsonplaceholder-v1.herokuapp.com/api/todos/' + todo.id, {
                title: title,
                completed: completed
            }).then((result) => {
                this.todos[index].title = title
                this.todos[index].completed = completed
                console.log('succcess');
            }).catch((err) => {
                console.error(err);
            });
        },
        deleteTodo(todo) {
            const index = this.todos.findIndex(e => e.id == todo.id)

            axios.delete('https://jsonplaceholder-v1.herokuapp.com/api/todos/' + todo.id,)
                .then((result) => {
                    this.todos.splice(index, 1);
                    console.log('success');
                }).catch((err) => {
                    console.error(err);
                });
        },
        addTodo() {
            axios.post('https://jsonplaceholder-v1.herokuapp.com/api/users/1/todos', {
                title: this.form.title,
                completed: false,
            }).then((result) => {
                this.todos.push(result.data.data)
                this.showModalTodo = false
                this.form.title = null
                console.log(JSON.stringify(result.data.data));
            }).catch((err) => {
                console.error(err);
            });
        },
        toggleModal() {
            this.showModalTodo = !this.showModalTodo
            this.$nextTick(() => this.$refs.title.focus())
        }
    },
}
</script>