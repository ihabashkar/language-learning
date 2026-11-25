A language learning application focused strictly on **Modern Standard Arabic (MSA)**. The project is also a hands-on way to learn full-stack application development: programming languages and syntax, APIs, databases, and system design.

## Project status

This repository is at the planning stage. The architecture and features below describe a proposed first version; they are not claims that the application has already been built or that lesson content has been validated.

## Goals and scope

The first version is intended to help a learner study MSA through structured lessons and practice. It should keep language content, learning progress, and application behavior understandable enough to serve as a learning project in its own right.

The language scope is MSA only. Regional dialect instruction is out of scope for the initial version. The app should distinguish Modern Standard Arabic from Classical Arabic where relevant, and lesson material should be reviewed for accuracy before being presented as authoritative.

## Proposed first version

The initial product is a locally run web application. A learner would be able to:

- Browse a small set of beginner lessons organized by topic or level.
- Study Arabic words and example sentences with translations and notes.
- Complete simple practice questions, such as matching, multiple choice, or typed answers.
- See basic progress saved between sessions on the same installation.

These are proposed features, not implemented functionality. Accounts, synchronization across devices, audio, speech recognition, and a large curriculum are not part of the initial design. They can be considered later if they can be added without violating the no-cost constraint.

## How the application is intended to work

The proposed application has three main parts:

1. **Web interface:** Runs in a browser and displays lessons, exercises, and progress. Arabic content should render right-to-left where appropriate while keeping mixed Arabic and Latin text readable.
2. **Backend API:** A local server provides structured lesson data and handles actions such as recording a completed exercise. The browser communicates with it through HTTP endpoints that return JSON.
3. **Database:** A local database stores lesson content and learner progress. The first version can use SQLite, which keeps data in a file and does not require a separate database server.

In a typical interaction, the browser requests lesson data from the API, the backend reads that data from the database and returns it, and the browser displays the lesson. When a learner completes an exercise, the browser sends the result to the API and the backend records the progress in the database.

This is a proposed learning architecture, not a statement about an existing implementation. Keeping the first deployment local avoids requiring a paid hosting, database, or authentication service. It also means the initial version is intended for one learner on one installation rather than a publicly available multi-user service.

## Cost constraint

The project must not require a paid service, subscription, license, or usage-based feature to develop and use in its initial form. The design therefore favors free, locally run software and does not depend on cloud hosting, hosted databases, paid AI APIs, or commercial language-content APIs.

“Free” here means no required payment to a software or service provider. A computer, electricity, and internet access may still have their ordinary costs. Public deployment, domain registration, optional services, and changing free tiers are not assumed. Any later addition must be checked for cost before adoption; a free tier is not a guarantee of permanent zero cost.

## Proposed software

The following is a starting proposal, not a finalized or installed dependency list:

- **JavaScript** for the browser interface and backend, reducing the number of languages needed at the start.
- **React** for composing the user interface.
- **Vite** for local frontend development and building the browser assets.
- **Node.js** for running the backend locally.
- **Express** for defining HTTP API routes.
- **SQLite** for local persistent storage.
- **Git** for version history. A hosted Git service is optional and not required to run the app.

Before adding dependencies, check their licenses, maintenance status, and whether they introduce any paid service requirement. Software licensing being free does not make a hosted service free.

## Content and accuracy

Lesson content is central to the app and must be treated as data that needs review. The initial content should focus on MSA vocabulary, grammar, and examples. Translations and grammatical explanations should be checked against reliable references or by a qualified reviewer before the app presents them as correct. No external content source or review process has been selected yet.

## Possible development sequence

1. Set up a small frontend and backend that run locally.
2. Define a simple lesson and exercise data format.
3. Create a small, reviewed MSA lesson set.
4. Add practice interactions and save progress in SQLite.
5. Document how to run the application and how the API and database fit together.

This sequence is an initial direction and can change as the project develops.
