# 🤖 Simple Agent Demo

A practical demonstration of building **orchestrator and sub-agent patterns** for GitHub Copilot. This repository showcases how to structure and coordinate multiple specialized agents to solve complex, multi-faceted development tasks efficiently.

## 🎯 What's Inside

This demo repository contains a complete example of how to break down a complex development project into smaller, manageable tasks using GitHub Copilot agents. It uses a **dad joke collection application** as a concrete example—but the patterns apply to any development workflow.

### The Pattern in Action

```
┌─────────────────────────────────────────┐
│  Orchestrator Agent (Main Conductor)    │
│  "Break this down into smaller tasks"   │
└────────┬────────────────────────────────┘
         │
    ┌────┴────┬──────────┬──────────┐
    │          │          │          │
    ▼          ▼          ▼          ▼
┌────────┐ ┌────────┐ ┌────────┐ ┌────────┐
│ Planner│ │ Coder  │ │Designer│ │Validator
│ Agent  │ │ Agent  │ │ Agent  │ │ Agent
└────────┘ └────────┘ └────────┘ └────────┘
```

The **Orchestrator** coordinates specialized agents:
- **Planner**: Breaks down requirements and creates implementation plans
- **Coder**: Writes and refactors application code
- **Designer**: Handles UI/UX design and styling
- **Validator**: Reviews quality and identifies issues

## 📂 Repository Structure

```
.
├── .github/
│   ├── agents/                    # Agent definitions
│   │   ├── orchestrator.agent.md  # Main conductor agent
│   │   ├── planner.agent.md       # Planning & analysis agent
│   │   ├── coder.agent.md         # Code generation agent
│   │   └── designer.agent.md      # UI/UX design agent
│   ├── copilot-instructions.md    # Repository-wide conventions
│   └── instructions/              # Specialized instructions
├── Data/
│   └── Jokes.json                 # Sample dataset (jokes)
├── docs/
│   └── Starter-Prompts.md         # Example prompts to get started
└── README.md                      # You are here! 👈
```

## 🚀 Quick Start

### 1. Explore the Agents

Each agent is defined in `.github/agents/`. Open them to understand the specialized role of each:

```bash
# View the orchestrator agent
cat .github/agents/orchestrator.agent.md

# View other specialized agents
cat .github/agents/planner.agent.md
cat .github/agents/coder.agent.md
cat .github/agents/designer.agent.md
```

### 2. Review Starter Prompts

Check `docs/Starter-Prompts.md` to see example prompts that demonstrate how to use the orchestrator pattern:

```bash
cat docs/Starter-Prompts.md
```

### 3. Sample Data

The repository includes a sample `Data/Jokes.json` file with dad jokes. This is used in the starter prompts to demonstrate:
- How agents handle real-world data
- How to structure datasets for agent consumption
- How agents coordinate to process information

## 💡 How to Use This Demo

### Example: Building a New Application

Use the **Orchestrator agent** to break down your requirements:

> "I want to create a web app that showcases my joke collection. It should be a .NET 10 Blazor + Aspire application deployed to Azure Container Apps with a clean, responsive design.
> 
> Use the Orchestrator agent to break down the task into smaller steps and call other agents for each step: frontend, backend, and deployment automation."

The Orchestrator will:
1. ✅ Call the **Planner** to break down requirements
2. ✅ Call the **Coder** to build frontend and backend
3. ✅ Call the **Designer** to refine the UI
4. ✅ Coordinate everything into a cohesive solution

### Agent Coordination Benefits

| Benefit | Details |
|---------|---------|
| **Specialization** | Each agent has focused expertise in a specific domain |
| **Quality** | Different perspectives reduce blind spots |
| **Speed** | Parallel agent execution accelerates development |
| **Maintainability** | Clear agent responsibilities make code easier to manage |
| **Scalability** | Add new agents without disrupting existing ones |

## 🏗️ Key Design Principles

### 1. **Single Responsibility**
Each agent has one clear purpose—no multi-role confusion.

### 2. **Clear Communication**
Agents pass context and results explicitly between calls.

### 3. **Orchestrator as Conductor**
The Orchestrator doesn't do the work; it coordinates who does.

### 4. **Reusability**
Agents can be called independently or as part of a workflow.

### 5. **Convention Over Configuration**
Follow the coding standards in `.github/copilot-instructions.md` for consistency.

## 📚 Learning Resources

- **Agent Definitions**: See `.github/agents/*.agent.md` for how each agent is configured
- **Repository Standards**: `.github/copilot-instructions.md` documents coding conventions
- **Example Prompts**: `docs/Starter-Prompts.md` shows real-world usage patterns
- **Sample Data**: `Data/Jokes.json` demonstrates data structure

## 🎓 Practical Example: Dad Joke App

This demo uses a complete dad joke collection app as the example:

### What Gets Built
- ✅ .NET 10 Blazor frontend with responsive design
- ✅ .NET 10 backend API for joke retrieval & search
- ✅ Azure Container Apps deployment
- ✅ GitHub Actions CI/CD automation
- ✅ Bicep infrastructure code

### How Agents Work Together
1. **Orchestrator** receives the full requirement
2. **Planner** creates an implementation roadmap
3. **Coder** builds backend API endpoints
4. **Coder** builds Blazor components
5. **Designer** refines UI/UX and styling
6. **Coder** creates deployment infrastructure
7. **Orchestrator** coordinates validation and integration

## � The Origin Story: A Comedy of Agents

Here's how this demo came to be:

**Day 1 - The Brainstorm:**
> A developer walks up to the **Orchestrator** and says: "Build me an app that showcases dad jokes."

The Orchestrator looks confused. "That's... vague. And why are we building an app about jokes when we ARE the jokes?" It then does what it does best—delegates.

**Day 2 - The Planning Chaos:**
The **Planner** agent creates a 50-page implementation roadmap with sections like "Microservices Architecture for Joke Delivery" and "Distributed Caching Strategy for Punchlines." 

Meanwhile, the **Coder** agent is scrolling through and muttering: "Did we really need to architect this like we're managing Netflix? It's Dad. Jokes."

**Day 3 - The Designer's Existential Crisis:**
The **Designer** agent opens the first UI mockup and says: "Why is everything Comic Sans? This is an app FOR dad jokes, not a dad joke ITSELF."

After heated negotiations (and several iterations), a design is approved. The result? Clean, responsive, and absolutely joke-proof (or proof-of-joke?).

**Day 4 - The Integration Nightmare:**
All agents try to work together. The **Coder** built a masterpiece. The **Designer** made it beautiful. The **Planner** insists there's a missing microservice nobody asked for.

The **Orchestrator** (pulling its hair out, if it had any) says: "Can we PLEASE just ship this?"

**Day 5 - The Realization:**
The app works perfectly. Users are laughing (though debatably AT or WITH the jokes). Agents high-five (digitally).

**The Moral:** When you have too many smart agents in a room, you either get a masterpiece... or you get over-engineered. Sometimes both. This demo proves that with the right orchestration, you can achieve harmony among specialized agents—even when they're all built to second-guess each other.

(Honestly, the agents had to coordinate better than a team of comedians working off one script. But somehow... it worked. 🎬)

## �🔧 Customizing for Your Needs

### To Create New Agents
1. Create a new file in `.github/agents/` following the naming convention: `{agent-name}.agent.md`
2. Define the agent's purpose, capabilities, and constraints
3. Reference it from the Orchestrator or other coordinating agents

### To Modify Instructions
Update `.github/copilot-instructions.md` with your project-specific:
- Code style preferences
- Naming conventions
- Folder structure requirements
- Technology stack choices

## 🎬 Next Steps

1. **Fork or clone** this repository
2. **Review** the agent definitions in `.github/agents/`
3. **Read** the starter prompts in `docs/Starter-Prompts.md`
4. **Try** using the Orchestrator with your own requirements
5. **Customize** the agents to match your project needs
6. **Share** your improvements back to the community

## 🤝 Contributing

Have improvements or new agent patterns? Contributions are welcome! This demo is meant to evolve and showcase best practices for GitHub Copilot agent coordination.

## 📝 License

This repository is a public demonstration of GitHub Copilot agent patterns. Feel free to use, modify, and learn from it!

---

## 🎯 Key Takeaways

- **Agents = Specialized AI Contributors**: Each with focused expertise
- **Orchestrators = Conductors**: They don't write code; they coordinate
- **Patterns > Perfection**: Use these patterns as templates for your projects
- **Scalability**: Start simple, add complexity as needed
- **Community**: Share what you learn with other developers

---

**Happy agent building! 🚀**
