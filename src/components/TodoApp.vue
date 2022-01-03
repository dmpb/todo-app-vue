<template>
    <div class="relative h-full pb-32">
        <div class="p-4 bg-slate-50">
            <div class="container relative max-w-lg mx-auto">
                <h1 class="text-3xl font-bold text-left text-blue-600">Todo App</h1>
            </div>
        </div>
        <div class="container relative max-w-lg pt-6 mx-auto">
            <div class="p-4 rounded-md shadow-md shadow-slate-200">
                <div class="flex justify-between mb-2">
                    <div class="flex">
                        <div class="flex-auto">
                            <input type="checkbox" id="list-1" class="mr-4" />
                        </div>
                        <label for="list-1">Hacer la tarea de matemática a las 10:30 de la mañana</label>
                    </div>
                    <button class="ml-4">
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
                <div class="flex justify-between mb-2">
                    <div class="flex">
                        <div class="flex-auto">
                            <input type="checkbox" id="list-1" class="mr-4" />
                        </div>
                        <label for="list-1">Dormir temprano</label>
                    </div>
                    <button class="ml-4">
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
                <button class="font-bold text-blue-600">+ Nuevo Recordatorio</button>
            </div>
        </div>
    </div>
</template>
<script>
export default {

}
</script>