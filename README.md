# Dengshi

Dengshi AI - A GeoGuessr-Inspired Dengue Prevention Web App**
Project Overview
Dengshi is a gamified web application inspired by GeoGuessr, designed to tackle dengue outbreaks in Bangladesh. Players explore locations, guess mosquito-prone areas, and contribute by capturing real-time images of potential dengue hotspots. These contributions are analyzed using a machine learning model trained on 107 images through Teachable Machine. The app also provides real-time preventive measures to users based on identified risks.

Key Features
GeoGuessr-Inspired Gameplay:

Players guess locations in Bangladesh prone to mosquitoes.
Earn points and extra lives through accurate guesses and contributions.
Real-Time Image Contribution:

Players can capture and upload images of damp areas or stagnant water when their lives run out.
Images are analyzed to predict dengue hotspots.
AI-Powered Analysis:

Uses a Teachable Machine pre-trained model to classify images for dengue-prone elements.
Identifies areas with stagnant water, damp walls, and other mosquito-breeding indicators.
Dengue Prevention Measures:

Provides real-time preventive tips tailored to identified risks in a user’s area.
Aggregates data for city corporations to assist in proactive measures.
Leaderboard and Rewards:

Gamified leaderboard to encourage contributions.
Players earn badges and extra lives for consistent participation.
Tech Stack
Frontend: Next.js, React.js
Backend: Firebase (Authentication, Firestore, Cloud Storage, Hosting)
AI/ML: Teachable Machine (Custom model trained on 107 images of dengue-prone elements)
Libraries:
@tensorflow/tfjs: TensorFlow.js for model integration.
@teachablemachine/image: For loading and using Teachable Machine models.
Dependencies
{
  "type": "commonjs",
  "dependencies": {
    "@teachablemachine/image": "^0.8.5",
    "@tensorflow/tfjs": "^4.22.0",
    "firebase": "^11.2.0",
    "next": "^15.1.5",
    "react": "^19.0.0",
    "react-dom": "^19.0.0"
  }
}
Setup Instructions
Follow these steps to set up and run the project locally:

Clone the Repository:

git clone https://github.com/<your-repo-name>.git
cd dengshi
Install Dependencies: Ensure you have Node.js and npm installed. Then, run:

npm install
Set Up Firebase:

Create a Firebase project on the Firebase Console.
Enable Authentication, Firestore, and Cloud Storage.
Add your Firebase config in src/firebase-config.js:
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_AUTH_DOMAIN",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_STORAGE_BUCKET",
  messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
  appId: "YOUR_APP_ID",
};
export default firebaseConfig;
Integrate Teachable Machine Model:

Export your trained Teachable Machine model and upload it to Firebase Cloud Storage.
Use TensorFlow.js to load and run the model in the app:
import * as tmImage from '@teachablemachine/image';

const loadModel = async () => {
  const modelURL = '/path/to/teachable-machine/model.json';
  const metadataURL = '/path/to/teachable-machine/metadata.json';
  const model = await tmImage.load(modelURL, metadataURL);
  return model;
};
Run the App: Start the development server:

npm run dev
Deploy to Firebase:

firebase deploy
How It Works
Gameplay:

Players guess mosquito-prone locations and earn points for correct answers.
When lives run out, they are prompted to capture and upload images of potential hotspots.
Image Analysis:

Uploaded images are processed using the Teachable Machine model to detect elements like stagnant water or damp areas.
Results are stored in Firestore for analysis and shared with city corporations.
Preventive Measures:

The app displays dengue prevention tips based on identified risks (e.g., use mosquito nets, avoid standing water).
Community Impact:

Aggregated data predicts mosquito hotspots 3-4 months in advance.
Reports are shared with city corporations for proactive action.
Collaborators
Mehreen Mallick Fiona

LinkedIn: Mehreen Mallick Fiona
GitHub: Noblesse013
Mahdi Hasan

LinkedIn: Mahdi Hasan
GitHub: eeemrann
Safwat Bushra Afreen

LinkedIn: Safwat Bushra Afreen
GitHub: Safwatbushra
Future Enhancements
Add support for multi-language interfaces to cater to diverse users in Bangladesh.
Improve image processing using Firebase ML or external AI services.
Introduce SMS or email alerts for users in high-risk areas.
Enable users to share their achievements and preventive tips on social media.
Contributing
We welcome contributions! To contribute:

Fork the repository.
Create a feature branch:
git checkout -b feature-name
Commit changes and push:
git commit -m "Add new feature"
git push origin feature-name
Submit a pull request.
