# pruebas-del-codigo-
using System;
using Xunit;

namespace YourNamespace.Tests
{
    public class ProgramTests
    {
        [Fact]
        public void VerifyInitialState()
        {
            // Arrange
            var estadoCamarasEsperado = new string[] { "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada" };
            var estadoSensoresEsperado = new bool[] { false, false, false, false, false, false, false, false, false, false, false, false, false, false, false, false };

            // Act
            var programa = new Program();

            // Assert
            Assert.Equal(estadoCamarasEsperado, programa.estadoCamaras);
            Assert.Equal(estadoSensoresEsperado, programa.estadoSensores);
        }

        [Fact]
        public void ActivateAllCameras_ShouldSetAllCamerasToActivated()
        {
            // Arrange
            var programa = new Program();
            var estadoCamarasEsperado = new string[] { "activada", "activada", "activada", "activada", "activada", "activada", "activada", "activada", "activada", "activada", "activada", "activada", "activada", "activada", "activada", "activada" };

            // Act
            programa.ActivarTodasLasCamaras();

            // Assert
            Assert.Equal(estadoCamarasEsperado, programa.estadoCamaras);
        }

        [Fact]
        public void DeactivateAllCameras_ShouldSetAllCamerasToDeactivated()
        {
            // Arrange
            var programa = new Program();
            var estadoCamarasEsperado = new string[] { "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada" };

            // Act
            programa.DesactivarTodasLasCamaras();

            // Assert
            Assert.Equal(estadoCamarasEsperado, programa.estadoCamaras);
        }

        [Fact]
        public void ActivateCamera_ShouldActivateSpecifiedCamera()
        {
            // Arrange
            var programa = new Program();
            var camara = 3;
            var estadoCamarasEsperado = new string[] { "desactivada", "desactivada", "activada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada" };

            // Act
            programa.ActivarCamara(camara);

            // Assert
            Assert.Equal(estadoCamarasEsperado, programa.estadoCamaras);
        }

        [Fact]
        public void DeactivateCamera_ShouldDeactivateSpecifiedCamera()
        {
            // Arrange
            var programa = new Program();
            var camara = 1;
            var estadoCamarasEsperado = new string[] { "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada", "desactivada" };

            // Act
            programa.DesactivarCamara(camara);

            // Assert
            Assert.Equal(estadoCamarasEsperado, programa.estadoCamaras);
        }

        [Fact]
        public void ActivateAllMotionSensors_ShouldSetAllSensorsToActivated()
        {
            // Arrange
            var programa = new Program();
            var estadoSensoresEsperado = new bool[] { true, true, true, true, true, true, true, true, true, true, true, true, true, true, true, true };

            // Act
            programa.ActivarTodosLosSensores();

            // Assert
            Assert.Equal(estadoSensoresEsperado, programa.estadoSensores);
        }

        [Fact]
        public void DeactivateAllMotionSensors_ShouldSetAllSensorsToDeactivated()
        {
            // Arrange
            var programa = new Program();
            var estadoSensoresEsperado = new bool[] { false, false, false, false, false, false, false, false, false, false, false, false, false, false, false, false };

            // Act
            programa.DesactivarTodosLosSensores();

            // Assert
            Assert.Equal(estadoSensoresEsperado, programa.estadoSensores);
        }

        [Fact]
        public void ActivateMotionSensor_ShouldActivateSpecifiedSensor()
        {
            // Arrange
            var programa = new Program();
            var sensor = 2;
            var estadoSensoresEsperado = new bool[] { false, true, false, false, false, false, false, false, false, false, false, false, false, false, false, false };

            // Act
            programa.ActivarSensor(sensor);

            // Assert
            Assert.Equal(estadoSensoresEsperado, programa.estadoSensores);
        }

        [Fact]
        public void DeactivateMotionSensor_ShouldDeactivateSpecifiedSensor()
        {
            // Arrange
            var programa = new Program();
            var sensor = 4;
            var estadoSensoresEsperado = new bool[] { false, false, false, false, true, false, false, false, false, false, false, false, false, false, false, false };

            // Act
            programa.DesactivarSensor(sensor);

            // Assert
            Assert.Equal(estadoSensoresEsperado, programa.estadoSensores);
        }
    }
}










