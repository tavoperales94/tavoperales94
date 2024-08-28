- 👋import React, { useState } from 'react';
import { ChevronLeft, ChevronRight } from 'lucide-react';

const Presentacion = () => {
  const [diapositivaActual, setDiapositivaActual] = useState(0);

  const diapositivas = [
    {
      titulo: "La Erosión: Modelando Nuestra Tierra",
      contenido: (
        <>
          <p>La erosión es un conjunto de fenómenos exteriores que modifican las formas del relieve creadas por la geodinámica interna.</p>
          <p>Su tendencia es nivelar la superficie terrestre.</p>
          <p>Agentes principales: ríos, aguas subterráneas, olas, vientos, glaciares y agentes atmosféricos como lluvia y nieve.</p>
        </>
      )
    },
    {
      titulo: "Los Tres Procesos de la Erosión",
      contenido: (
        <ol className="list-decimal list-inside">
          <li>Desintegración: Desagregación o arranque físico de los materiales</li>
          <li>Transporte: Desplazamiento de los materiales erosionados</li>
          <li>Depositación: Acumulación de materiales en zonas más bajas</li>
        </ol>
      )
    },
    {
      titulo: "Tipos de Erosión",
      contenido: (
        <ul className="list-disc list-inside">
          <li>Erosión Fluvial (Ríos)</li>
          <li>Erosión Eólica (Viento)</li>
          <li>Erosión Marina</li>
          <li>Erosión Glaciar</li>
          <li>Erosión Kárstica</li>
          <li>Erosión Pluvial (Lluvia)</li>
        </ul>
      )
    },
    {
      titulo: "Erosión Fluvial",
      contenido: (
        <>
          <p>Causada por el agua de los ríos que desgasta las superficies y arrastra restos de material.</p>
          <p>Relieves de degradación: Valles en "V", meandros, cañones</p>
          <p>Relieves de agradación: Conos de deyección, terrazas, deltas</p>
        </>
      )
    },
    {
      titulo: "Erosión Eólica",
      contenido: (
        <>
          <p>Producida por la acción del viento, que transporta pequeñas partículas de rocas.</p>
          <p>Relieves de degradación: Pedestal, bosque de rocas</p>
          <p>Relieves de agradación: Dunas, médanos</p>
        </>
      )
    },
    {
      titulo: "Erosión Marina",
      contenido: (
        <>
          <p>Destrucción de los litorales principalmente por la acción de las olas y las corrientes.</p>
          <p>Relieves de degradación: Penínsulas, bahías, acantilados</p>
          <p>Relieves de agradación: Playas, tómbolos</p>
        </>
      )
    },
    {
      titulo: "Erosión Glaciar",
      contenido: (
        <>
          <p>Causada por grandes masas de hielo que descienden lentamente por los valles.</p>
          <p>Relieves de degradación: Valles en "U", circo glaciar</p>
          <p>Relieves de agradación: Morrenas, drumlins</p>
        </>
      )
    },
    {
      titulo: "Erosión Kárstica",
      contenido: (
        <>
          <p>Disolución de las rocas calizas por la acción de aguas ligeramente ácidas que contienen dióxido de carbono.</p>
          <p>Relieves de degradación: Sumideros, cavernas</p>
          <p>Relieves de agradación: Estalagmitas, estalactitas</p>
        </>
      )
    },
    {
      titulo: "Erosión Pluvial",
      contenido: (
        <>
          <p>Se produce cuando las gotas de lluvia golpean el suelo, arrastrando partículas.</p>
          <p>Relieves de degradación: Surcos, cárcavas</p>
          <p>Relieves de agradación: Abanicos coluviales</p>
        </>
      )
    },
    {
      titulo: "Conclusión",
      contenido: (
        <>
          <p>La erosión es un proceso complejo que modela la superficie de nuestro planeta.</p>
          <p>Implica la desintegración, el transporte y la depositación de materiales.</p>
          <p>Diferentes tipos de erosión crean relieves y características únicas.</p>
          <p>Comprender la erosión es crucial para la geología, la geografía y los estudios ambientales.</p>
        </>
      )
    }
  ];

  const siguienteDiapositiva = () => {
    setDiapositivaActual((prev) => (prev + 1) % diapositivas.length);
  };

  const diapositivaAnterior = () => {
    setDiapositivaActual((prev) => (prev - 1 + diapositivas.length) % diapositivas.length);
  };

  return (
    <div className="flex flex-col items-center justify-center h-screen bg-gray-100">
      <div className="w-full max-w-3xl bg-white rounded-lg shadow-lg p-6">
        <h1 className="text-3xl font-bold mb-4">{diapositivas[diapositivaActual].titulo}</h1>
        <div className="mb-6">{diapositivas[diapositivaActual].contenido}</div>
        <div className="flex justify-between items-center">
          <button onClick={diapositivaAnterior} className="flex items-center px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-600">
            <ChevronLeft className="mr-2" /> Anterior
          </button>
          <span className="text-gray-600">
            Diapositiva {diapositivaActual + 1} de {diapositivas.length}
          </span>
          <button onClick={siguienteDiapositiva} className="flex items-center px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-600">
            Siguiente <ChevronRight className="ml-2" />
          </button>
        </div>
      </div>
    </div>
  );
};

export default Presentacion;
