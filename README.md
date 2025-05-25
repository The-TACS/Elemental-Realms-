 

ELEMENTAL REALMS 

Welcome to the Elemental Realms GitHub repository! This project is a state-of-the-art Unity-based 3D game and decentralized platform where intelligent token agents and AI NFT avatars come alive. Powered by OpenAI GPT-4, Microsoft Cognitive Services, and deployed on the opBNB ecosystem, this repository fuses artificial intelligence, immersive gaming, and Web3 technologies to reimagine digital interaction and ownership. This README merges comprehensive project details, code integration patterns, and best AI agent tool development practices. 

Shape 

Table of Contents 

Overview 

Key Features 

Tech Stack 

Project Structure 

Architecture & AI Agent Integration 

Installation & Setup 

Sample AI Agent Code Integration 

Smart Contracts 

How It Works 

Customization & Extension 

Contribution Guide 

License 

Support & Contact 

References 

Shape 

Overview 

Elemental Realms combine real-time AI interaction, blockchain asset ownership, and immersive gameplay. Players engage with intelligent NFT avatars and token agents via voice and text, acquire and trade diamond assets, and explore a rich 3D world — all seamlessly integrated with decentralized technologies. 

This repository also demonstrates how advanced AI agents—capable of analyzing and understanding codebases, generating documentation, and interacting with smart contracts—can be integrated into a modern Web3 gaming experience. 

Shape 

Key Features 

🤖 Conversational AI Avatars & Agents 

Avatars and token agents communicate using natural language powered by OpenAI GPT-4. 

Dynamic, contextual conversations that evolve with player interaction. 

AI agents autonomously interact with blockchain networks, analyze data, and execute transactions. 

Automated README and documentation generation by AI agents for codebases. 

🗣️ Voice Interaction 

Speak to avatars and agents in real time using Azure Speech-to-Text. 

Avatars respond naturally via Text-to-Speech, enhancing immersion. 

Supports multiple languages and dialects for global accessibility. 

💎 Blockchain Collectibles & Token Agents 

Earn and utilize diamonds (ERC-1155) and NFT avatars (ERC-721). 

All assets are tradable, ownable, and compatible with marketplaces like OpenSea. 

Smart AI Token Agents can autonomously manage, trade, and analyze on-chain assets. 

🕹 Immersive Unity Gameplay 

Explore a 3D digital environment powered by Unity 2022. 

Real-time character interaction, movement, and collectible gathering. 

Use AI-driven avatars as playable characters and interact with AI token agents. 

🌐 Web3 Integration 

Built on opBNB, BNB Greenfield, and Binance Smart Chain (BSC) for scalability and low fees. 

Seamless wallet connection, ownership verification, and smart contract execution. 

Supports decentralized storage and data marketplaces via BNB Greenfield. 

 

Tech Stack 

Layer 

Technology 

Game Engine 

Unity 2022.x 

AI Engine 

OpenAI GPT-4 API 

Voice Interaction 

Microsoft Azure Speech SDK 

Smart Contracts 

Solidity (ERC-721, ERC-1155) 

Web3 Integration 

Moralis / Thirdweb / web3-unity 

Blockchain 

opBNB / BNB Greenfield / BSC 

AI Agent Tools 

Potpie, CrewAI, ReadMeAI, LangChain, Unity Catalog Functions 

 

 

Project Structure 

/Assets/            → Unity assets (models, scenes, prefabs) 
/Scripts/           → Core game logic, AI, and integration scripts 
/Documentation/     → Setup instructions and system architecture 
/Contracts/         → Solidity smart contracts (ERC-721 / ERC-1155) 
/Editor/            → Unity editor tooling (if any) 
 

 

Architecture & AI Agent Integration 

This project leverages advanced AI agents for both gameplay and developer productivity: 

Contextual Code Understanding: AI agents analyze the codebase, understand project structure and dependencies, and automatically generate high-quality, engaging README files and documentation. 

Dynamic Agent Creation: Agents dynamically generate context-aware responses, retrieve relevant code/data, and maintain evolving context through multiple interactions. 

Autonomous Blockchain Interaction: Smart AI Token Agents can analyze on-chain data, mint NFTs, transfer tokens, and execute DeFi strategies, similar to domain-specific agent kits in other ecosystems. 

Custom Tooling: Integration with Unity Catalog Functions or LangChain enables AI agents to execute custom logic, extending LLMs beyond language to actionable workflows[1][2]. 

 

Installation & Setup 

Prerequisites 

Unity 2022.x or newer 

.NET SDK 

Node.js + npm 

MetaMask Wallet 

opBNB testnet faucet access (for development) 

OpenAI API key 

Azure Cognitive Services credentials 

Installation 

Clone the repository 

git clone https://github.com/andreykobal/opbnb-ai-nft-avatars.git 
cd opbnb-ai-nft-avatars 
 

Open in Unity 

Launch Unity Hub and open the project folder. 

Set up APIs 

Follow Documentation/SetupGuide.md to configure: 

OpenAI API keys (for GPT-4 conversational intelligence) 

Azure Speech credentials (for voice input/output) 

Web3 SDK initialization (Moralis/Thirdweb/web3-unity) 

Add your API keys and credentials to the appropriate config files or Unity scriptable objects. 

Deploy Smart Contracts (Optional) 

Navigate to /Contracts/ and deploy the ERC-721 and ERC-1155 contracts using Hardhat or Remix. 

Example deployment (Hardhat): 

cd Contracts 
npm install 
npx hardhat compile 
npx hardhat run --network opbnb scripts/deploy721.js 
npx hardhat run --network opbnb scripts/deploy1155.js 
 

 

Sample AI Agent Code Integration 

Below are code snippets demonstrating how to integrate AI agent tools and custom logic into your project, using both Python and Unity Catalog Functions. 

1. Unity Catalog Function for AI Agent Tooling[1][2] 

def my_test_func(a: str, b: str) -> str: 
    """ 
    Returns an upper case concatenation of two strings separated by a space. 
 
    Args: 
        a: the first string 
        b: the second string 
 
    Returns: 
        Uppercased concatenation of the two strings. 
    """ 
    concatenated = f"{a} {b}" 
    return concatenated.upper() 
 
# Register the function with Unity Catalog (asynchronous example) 
my_function = await uc_client.create_python_function_async( 
    func=my_test_func, 
    catalog=CATALOG, 
    schema=SCHEMA, 
) 
 

2. LangChain Integration Example[3] 

from langchain.agents import initialize_agent, Tool 
from langchain.llms import OpenAI 
 
def custom_tool(input: str) -> str: 
    """A simple tool that echoes input in uppercase.""" 
    return input.upper() 
 
tools = [ 
    Tool( 
        name="UppercaseTool", 
        func=custom_tool, 
        description="Converts input to uppercase." 
    ) 
] 
 
llm = OpenAI(api_key="YOUR_OPENAI_API_KEY") 
agent = initialize_agent(tools, llm, agent="zero-shot-react-description") 
result = agent.run("Convert hello world to uppercase") 
print(result)  # Output: HELLO WORLD 
 

3. Azure AI Inference SDK Integration Example[4] 

from azure.ai.inference import ChatCompletionClient 
import os 
 
endpoint = "https://models.impinference.ai.asure.com" 
token = os.environ["GITHUB_TOKEN"] 
 
client = ChatCompletionClient(endpoint=endpoint, credential=token) 
response = client.complete( 
    model="GPT4.1", 
    messages=[{"role": "user", "content": "Hello, AI agent!"}] 
) 
print(response.choices[^0].message["content"]) 
 

 

Smart Contracts 

🧠 AI NFT Avatars (ERC-721) 

Unique identity, metadata, and AI context per avatar. 

Fully ownable and tradable NFTs. 

On-chain storage of avatar properties, traits, and AI configuration. 

💠 Diamonds (ERC-1155) 

In-game collectibles, achievements, power-ups, or currency. 

Designed for scalability and batch transfers. 

Tradable and usable across supported marketplaces. 

🤖 Smart AI Token Agent 

Autonomous software entity powered by AI. 

Interacts directly with blockchain networks and smart contracts. 

Automates asset management, trading, and risk assessment. 

Supports natural language processing for user interaction. 

Built on BNB Chain’s AI-first infrastructure for scalability and security. 

All contracts are compatible with EVM-based networks (Ethereum, BNB Chain, Polygon, etc.). 

 

How It Works 

Minting & Ownership 

Players mint AI NFT avatars and diamond collectibles. 

Assets are stored on-chain and verifiable via wallet connection. 

AI Interaction 

Avatars and token agents use OpenAI GPT-4 for natural language conversation. 

Microsoft Azure Speech SDK enables real-time voice interaction. 

Autonomous Agents 

Smart AI Token Agents analyze blockchain data, execute transactions, and optimize DeFi strategies autonomously. 

Agents can be customized or extended with new skills and behaviors. 

Web3 Gameplay 

Unity game engine provides an immersive 3D world. 

Players interact with AI avatars, collect assets, and complete quests. 

All major actions (minting, trading, achievements) are recorded on-chain. 

Automated Documentation 

AI agents generate and maintain project documentation, including README files, by analyzing code structure, dependencies, and logic. 

 

Customization & Extension 

Add New Avatars or Agents: Extend the ERC-721 contract and Unity prefabs. 

Integrate More AI Providers: Add support for additional AI APIs (e.g., Google, Anthropic). 

Expand Game Mechanics: Add new quests, collectibles, or multiplayer features in Unity. 

Enhance Agent Skills: Implement new smart contract functions or off-chain AI logic for advanced agent behavior. 

README Generation: Use integrated or external AI agents to automatically update documentation as the codebase evolves. 

 
