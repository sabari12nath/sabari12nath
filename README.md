import React, { useState, useEffect } from 'react';
import { Github, Twitter, Linkedin, Instagram, Mail, ExternalLink, Code2, Palette, Brain, Database, Server, Camera } from 'lucide-react';

const GitHubProfileUI = () => {
  const [isVisible, setIsVisible] = useState(false);
  const [currentTech, setCurrentTech] = useState(0);

  useEffect(() => {
    setIsVisible(true);
    const interval = setInterval(() => {
      setCurrentTech((prev) => (prev + 1) % techStack.length);
    }, 3000);
    return () => clearInterval(interval);
  }, []);

  const socialLinks = [
    { icon: Twitter, url: 'https://twitter.com/@modernzeuxis', label: 'Twitter', color: 'hover:text-blue-400' },
    { icon: Linkedin, url: 'https://linkedin.com/in/sabarinath-ps', label: 'LinkedIn', color: 'hover:text-blue-600' },
    { icon: Instagram, url: 'https://instagram.com/ft.shambu', label: 'Instagram', color: 'hover:text-pink-400' },
    { icon: Mail, url: 'mailto:psabarinath44@gmail.com', label: 'Email', color: 'hover:text-green-400' }
  ];

  const techStack = [
    { name: 'React', icon: '⚛️', category: 'Frontend' },
    { name: 'Next.js', icon: '▲', category: 'Framework' },
    { name: 'Python', icon: '🐍', category: 'Language' },
    { name: 'PyTorch', icon: '🔥', category: 'ML/AI' },
    { name: 'TensorFlow', icon: '🧠', category: 'ML/AI' },
    { name: 'Node.js', icon: '🟢', category: 'Backend' },
    { name: 'NestJS', icon: '🏠', category: 'Framework' },
    { name: 'MySQL', icon: '🗄️', category: 'Database' }
  ];

  const skills = [
    { icon: Code2, title: 'Frontend Development', desc: 'React, Next.js, JavaScript' },
    { icon: Palette, title: 'UI/UX Design', desc: 'Figma, Photoshop, Blender' },
    { icon: Brain, title: 'Machine Learning', desc: 'Python, PyTorch, TensorFlow' },
    { icon: Database, title: 'Backend', desc: 'Node.js, NestJS, MySQL' },
    { icon: Server, title: 'DevOps', desc: 'Appwrite, Cloud Services' },
    { icon: Camera, title: 'Creative', desc: 'Blender, Photoshop, Unity' }
  ];

  return (
    <div className="min-h-screen bg-gradient-to-br from-gray-900 via-purple-900 to-violet-900 text-white overflow-hidden">
      {/* Animated background particles */}
      <div className="absolute inset-0 overflow-hidden pointer-events-none">
        {[...Array(50)].map((_, i) => (
          <div
            key={i}
            className="absolute w-1 h-1 bg-white opacity-20 rounded-full animate-pulse"
            style={{
              left: `${Math.random() * 100}%`,
              top: `${Math.random() * 100}%`,
              animationDelay: `${Math.random() * 3}s`,
              animationDuration: `${2 + Math.random() * 3}s`
            }}
          />
        ))}
      </div>

      <div className="relative z-10 container mx-auto px-6 py-12">
        {/* Hero Section */}
        <div className={`text-center mb-16 transform transition-all duration-1000 ${isVisible ? 'translate-y-0 opacity-100' : 'translate-y-10 opacity-0'}`}>
          <div className="mb-8">
            <h1 className="text-6xl md:text-8xl font-bold bg-gradient-to-r from-cyan-400 via-purple-400 to-pink-400 bg-clip-text text-transparent mb-4">
              Hi 👋, I'm Sabarinath PS
            </h1>
            <div className="h-1 w-32 bg-gradient-to-r from-cyan-400 to-purple-400 mx-auto rounded-full mb-6"></div>
            <p className="text-2xl md:text-3xl text-gray-300 font-light">
              An aspiring beginner level frontend designer
            </p>
          </div>

          {/* Animated Tech Stack */}
          <div className="mb-12">
            <div className="bg-black/20 backdrop-blur-lg rounded-2xl p-8 border border-white/10">
              <h3 className="text-xl text-gray-300 mb-4">Currently Mastering</h3>
              <div className="flex items-center justify-center space-x-4">
                <div className="text-4xl">{techStack[currentTech].icon}</div>
                <div className="text-left">
                  <div className="text-2xl font-bold">{techStack[currentTech].name}</div>
                  <div className="text-sm text-purple-300">{techStack[currentTech].category}</div>
                </div>
              </div>
            </div>
          </div>

          {/* Social Links */}
          <div className="flex justify-center space-x-6 mb-12">
            {socialLinks.map((social, index) => (
              <a
                key={index}
                href={social.url}
                className={`p-4 bg-black/20 backdrop-blur-lg rounded-2xl border border-white/10 transition-all duration-300 hover:scale-110 hover:bg-white/10 ${social.color}`}
                target="_blank"
                rel="noopener noreferrer"
              >
                <social.icon size={28} />
              </a>
            ))}
          </div>
        </div>

        {/* Current Projects */}
        <div className="mb-16">
          <h2 className="text-4xl font-bold text-center mb-12 bg-gradient-to-r from-cyan-400 to-purple-400 bg-clip-text text-transparent">
            What I'm Working On
          </h2>
          <div className="grid md:grid-cols-2 gap-8">
            <div className="bg-black/20 backdrop-blur-lg rounded-2xl p-8 border border-white/10 hover:border-purple-400/50 transition-all duration-300">
              <div className="flex items-center mb-4">
                <div className="w-3 h-3 bg-green-400 rounded-full mr-3 animate-pulse"></div>
                <h3 className="text-xl font-semibold">Web Design Company Website</h3>
              </div>
              <p className="text-gray-300 mb-4">Building a modern, responsive website for a web designing company using cutting-edge technologies.</p>
              <a href="https://quaint-dogfish-868.convex.app" className="inline-flex items-center text-purple-400 hover:text-purple-300 transition-colors">
                View Project <ExternalLink size={16} className="ml-2" />
              </a>
            </div>
            
            <div className="bg-black/20 backdrop-blur-lg rounded-2xl p-8 border border-white/10 hover:border-cyan-400/50 transition-all duration-300">
              <div className="flex items-center mb-4">
                <div className="w-3 h-3 bg-blue-400 rounded-full mr-3 animate-pulse"></div>
                <h3 className="text-xl font-semibold">Learning Journey</h3>
              </div>
              <p className="text-gray-300 mb-4">Diving deep into Python, PyTorch, and TensorFlow to expand my machine learning capabilities.</p>
              <div className="flex space-x-2">
                <span className="px-3 py-1 bg-yellow-500/20 text-yellow-300 rounded-full text-sm">Python</span>
                <span className="px-3 py-1 bg-red-500/20 text-red-300 rounded-full text-sm">PyTorch</span>
                <span className="px-3 py-1 bg-orange-500/20 text-orange-300 rounded-full text-sm">TensorFlow</span>
              </div>
            </div>
          </div>
        </div>

        {/* Skills Grid */}
        <div className="mb-16">
          <h2 className="text-4xl font-bold text-center mb-12 bg-gradient-to-r from-cyan-400 to-purple-400 bg-clip-text text-transparent">
            Skills & Expertise
          </h2>
          <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
            {skills.map((skill, index) => (
              <div
                key={index}
                className="bg-black/20 backdrop-blur-lg rounded-2xl p-6 border border-white/10 hover:border-purple-400/50 transition-all duration-300 hover:scale-105"
              >
                <skill.icon size={32} className="text-purple-400 mb-4" />
                <h3 className="text-xl font-semibold mb-2">{skill.title}</h3>
                <p className="text-gray-300 text-sm">{skill.desc}</p>
              </div>
            ))}
          </div>
        </div>

        {/* Links Section */}
        <div className="text-center">
          <h2 className="text-4xl font-bold mb-12 bg-gradient-to-r from-cyan-400 to-purple-400 bg-clip-text text-transparent">
            Connect & Explore
          </h2>
          <div className="grid md:grid-cols-2 gap-6 max-w-4xl mx-auto">
            <a
              href="https://bento.me/sabarinath-ps"
              className="bg-black/20 backdrop-blur-lg rounded-2xl p-8 border border-white/10 hover:border-cyan-400/50 transition-all duration-300 hover:scale-105 block"
              target="_blank"
              rel="noopener noreferrer"
            >
              <Github size={32} className="text-cyan-400 mb-4 mx-auto" />
              <h3 className="text-xl font-semibold mb-2">All Projects</h3>
              <p className="text-gray-300">Check out my complete portfolio and projects</p>
            </a>
            
            <a
              href="https://docs.google.com/document/d/1Twyx-PKlZn6Ex-XyjQPmAjnpQ6gS15DZ/edit?usp=sharing&ouid=111807181711037922142&rtpof=true&sd=true"
              className="bg-black/20 backdrop-blur-lg rounded-2xl p-8 border border-white/10 hover:border-purple-400/50 transition-all duration-300 hover:scale-105 block"
              target="_blank"
              rel="noopener noreferrer"
            >
              <ExternalLink size={32} className="text-purple-400 mb-4 mx-auto" />
              <h3 className="text-xl font-semibold mb-2">My Experience</h3>
              <p className="text-gray-300">Learn about my professional journey and experiences</p>
            </a>
          </div>
        </div>

        {/* Footer */}
        <div className="mt-20 text-center">
          <p className="text-gray-400">
            💬 Ask me about <span className="text-purple-400 font-semibold">React, Next.js</span>
          </p>
          <p className="text-gray-400 mt-2">
            📫 Reach me at <a href="mailto:psabarinath44@gmail.com" className="text-cyan-400 hover:text-cyan-300 transition-colors">psabarinath44@gmail.com</a>
          </p>
        </div>
      </div>
    </div>
  );
};

export default GitHubProfileUI;
