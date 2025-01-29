# shortly-contemporary

import React from 'react';
import { motion } from 'framer-motion';

const images = [
  '/mnt/data/shortly contemporary art advisory Sophie Treppendahl.jpg',
  '/mnt/data/SHORTLY CONTEMPORARY ART ADVISORY HP copy.tiff',
  '/mnt/data/Shortly Contemporary Art Advisory Wanda Koop.jpg'
];

const Carousel = () => {
  return (
    <div className="relative w-full h-screen overflow-hidden">
      <motion.div
        className="absolute inset-0 flex"
        animate={{ x: [0, -100, -200, 0] }}
        transition={{ repeat: Infinity, duration: 15, ease: 'linear' }}
        style={{ width: `${images.length * 100}%` }}
      >
        {images.map((src, index) => (
          <img
            key={index}
            src={src}
            alt={`Slide ${index + 1}`}
            className="w-full h-screen object-cover"
            style={{ flex: '0 0 auto', width: '100%' }}
          />
        ))}
      </motion.div>
      <div className="absolute inset-0 flex flex-col items-center justify-center text-center">
        <h1 className="text-white text-5xl font-bold font-[Inter]">SHORTLY CONTEMPORARY</h1>
        <a
          href="mailto:bronwyn@shortlycontemporary.com"
          className="text-white text-xl mt-4 hover:underline"
        >
          bronwyn@shortlycontemporary.com
        </a>
      </div>
    </div>
  );
};

const LandingPage = () => {
  return (
    <div className="min-h-screen">
      <Carousel />
    </div>
  );
};

export default LandingPage;

