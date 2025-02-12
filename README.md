import React from "react";
import { motion } from "framer-motion"; // Animation library for smooth effects
import { FaGithub, FaLinkedin, FaEnvelope } from "react-icons/fa"; // Icons for social links
import { Card, CardContent } from "@/components/ui/card"; // UI components for a cleaner layout

// List of projects with details
const projects = [
  {
    title: "Project One",
    description: "A web application built using React and Firebase.",
    link: "#"
  },
  {
    title: "Project Two",
    description: "A REST API developed with Node.js and Express.",
    link: "#"
  },
  {
    title: "Project Three",
    description: "A portfolio website showcasing modern design trends.",
    link: "#"
  }
];

// Portfolio component
export default function Portfolio() {
  return (
    <div className="bg-gray-900 text-white min-h-screen p-6">
      {/* Page header */}
      <header className="text-center text-4xl font-bold mb-10">My Portfolio</header>
      
      {/* Project Showcase Section with animation */}
      <motion.section 
        className="grid md:grid-cols-3 gap-6"
        initial={{ opacity: 0 }} // Fade-in effect
        animate={{ opacity: 1 }}
        transition={{ duration: 1 }}
      >
        {projects.map((project, index) => (
          <Card key={index} className="bg-gray-800 p-4 rounded-2xl shadow-lg">
            <CardContent>
              {/* Project title and description */}
              <h2 className="text-xl font-semibold">{project.title}</h2>
              <p className="text-gray-400">{project.description}</p>
              
              {/* Project link */}
              <a 
                href={project.link} 
                className="text-blue-400 mt-2 inline-block hover:underline"
                target="_blank"
                rel="noopener noreferrer"
              >
                View Project
              </a>
            </CardContent>
          </Card>
        ))}
      </motion.section>
      
      {/* Footer section with contact details */}
      <footer className="text-center mt-10">
        <p>Contact Me:</p>
        <div className="flex justify-center gap-4 mt-2">
          {/* Email link */}
          <a href="mailto:varalakshmib103@gmail.com" className="text-blue-400 text-xl">
            <FaEnvelope />
          </a>
          {/* GitHub link */}
          <a href="https://github.com/varalakshmib2002/Varu" className="text-blue-400 text-xl">
            <FaGithub />
          </a>
          {/* LinkedIn link */}
          <a href="https://www.linkedin.com/in/varalakshmi-b-10811b201" className="text-blue-400 text-xl">
            <FaLinkedin />
          </a>
        </div>
      </footer>
    </div>
  );
}
