<template>
    <form>
        <div class="mb-3">
            <label class="form-label">Proyecto</label>
            <input type="text" class="form-control" required/>
        </div>

        <div class="mb-3">
            <label class="form-label">Actividad</label>
            <select class="form-select" required>
                <option disabled selected value="">Seleccione un tipo...</option>
                <option>Aplicación web con Vue.Js</option>
                <option>Backend Service con Node.Js</option>
                <option>App Movil con React Native</option>
            </select>
        </div>

        <div class="mb-3">
            <label class="form-check-label" for="exampleCheck1">Urgente</label>
            <input type="checkbox" class="form-check-input">
        </div>
        <button type="submit" class="btn btn-primary">Guardar</button>
    </form>
</template>