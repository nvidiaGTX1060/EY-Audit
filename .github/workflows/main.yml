name: Auditoría - Ejemplo básico EY

on:
  workflow_dispatch:
    inputs:
      modificar_alcance:
        description: '¿Necesitas modificar el alcance del proyecto?'
        type: boolean
        default: false
      archivo_alcance:
        description: 'Nombre del archivo con el nuevo alcance (si aplica)'
        required: false
      ejecutar_muestreo:
        description: '¿Ejecutar muestreo con EY Sample?'
        type: boolean
        default: true
      cantidad_muestra:
        description: 'Cantidad de registros a muestrear'
        required: false

jobs:
  modificar_alcance:
    if: ${{ github.event.inputs.modificar_alcance == 'true' }}
    runs-on: ubuntu-latest
    steps:
      - name: Mostrar mensaje de modificación de alcance
        run: echo "Modificación de alcance solicitada. Revisar y adjuntar el archivo: ${{ github.event.inputs.archivo_alcance }}"

  muestreo:
    if: ${{ github.event.inputs.ejecutar_muestreo == 'true' }}
    runs-on: ubuntu-latest
    steps:
      - name: Ejecutar muestreo con EY Sample
        run: |
          echo "Ejecutando proceso de muestreo con EY Sample"
          echo "Cantidad solicitada: ${{ github.event.inputs.cantidad_muestra }}"
          # Aquí podrías integrar el script de EY Sample si está disponible

  reporte:
    runs-on: ubuntu-latest
    needs: [modificar_alcance, muestreo]
    steps:
      - name: Generar reporte de auditoría
        run: echo "Generando reporte con los datos del alcance y muestreo realizados."
