# DJS08 Project Brief: React Router 

🎥 INSERT LOOM PRESENTATION LINK: [[Here](https://www.loom.com/share/86d0ab004c7240fd96254693557bb5f6?sid=343afaa9-6895-402b-b138-db7c94e84c75)]

After cloning the repo, run `npm install` to install the dependencies 

Are you ready to get stuck into some React Router? For this challenge, you are required to code along with the lecturer from this lesson on Scrimba V1 [VanLife Project Bootstrapping](https://v1.scrimba.com/learn/react/introduction-to-react-router-6-coafa4877a450245212825034) or on Scrimba V2 click the link here [VanLife Project Bootstrapping](https://v2.scrimba.com/advanced-react-c02h/~02d)

The starter code has all the CSS styling required for the project; you will just need to link the corresponding classes as you code along. Jump into the start code here: [GitHub Repository](https://github.com/CodeSpace-Academy/StudentNo_Classcode_Group_Name-Surname_DJS08/tree/main).

The focus for this project will be to understand routing and present your code. Along with your code, you will need to submit a recorded presentation talking through the presentation points included below.

## React Routing Presentation Talking Points

For your recorded presentation, you will be discussing key concepts related to React Router, an essential tool for building single-page applications. To illustrate your understanding, address the following three questions in your presentation. These questions are designed to test your knowledge of the content from the "Advanced React Routing" Van Life Project, including setup, functionality, and application of React Router.

### Question 1: Explain the Setup and Basic Configuration of React Router

**Key Points to Cover:**
- What is the purpose of using React Router in a React application?
- How do you set up React Router using `BrowserRouter` as shown in the lessons?
- Describe the role of the `<Routes>` and `<Route>` components in defining the navigation structure.

React Router is used in single-page applications (SPAs) to handle client-side routing. It allows you to navigate between different views (pages) of your app without requiring a full page reload. This makes the app feel faster and more dynamic because only the relevant content is updated in the DOM.

in order to use it you need to do the following:
run:
    npm install react-router-dom

then wrap where you want to route into a browserRouter, with routes forming with in (these can also be nested)

"import { BrowserRouter } from "react-router-dom";

function App() {
    return (
        <BrowserRouter>
            <Routes>
                <Route path="/" element={<Home />} />
                <Route path="/about" element={<About />} />
            </Routes>
        </BrowserRouter>
    );
}"

<Routes>: This is the container for all your route definitions. It tells React Router which route should be rendered based on the current URL.

<Route>: This is used to define individual routes. Each route specifies:

    A path (the URL).
    An element (the component that should be rendered for that path).

<Routes>
    <Route path="/" element={<Home />} />
    <Route path="/about" element={<About />} />
    <Route path="/contact" element={<Contact />} />
</Routes>


### Question 2: Application of Route Parameters and Nested Routes

**Key Points to Cover:**
- Explain what route parameters are and how they are used in React Router, including the use of `useParams()` to access these parameters.
    We can define route parameters using the colon : for dynamic parts of the URL in the case of this project it would be the ID of each of the cars pulling to a new page
    The useparams hook when inside the component can be used to retrieve the value of the parameter
        We define dynamic route parameters using a colon (:) in the path (e.g., /products/:id). When the component renders, we can access the parameter using the useParams() hook.

- Discuss the concept of nested routes as introduced in the lessons. What are nested routes, and how do they benefit the structure of a React application?
    nested routes are fairly simple as it is like any other nesting, where you are creating a route with in a route, this allows you to render components with in a route, such as a new NAV bar with out replacing the original NAV bar
        to be clear, nested route a rendered within the parent route, which helps when you are wanting to retain certain elements of the UI

- Provide an example, such as the configuration for nested routes in the VanLife project.

              <Route path="host" element={<HostLayout />}>
            <Route index element={<Dashboard />} />
            <Route path="income" element={<Income />} />
            <Route path="reviews" element={<Reviews />} />
            <Route path="vans" element={<HostVans />} />
            <Route path="vans/:id" element={<HostVanDetail />}>
              <Route index element={<HostVanInfo />} />
              <Route path="pricing" element={<HostVanPricing />} />
              <Route path="photos" element={<HostVanPhotos />} />
            </Route>
            </Route>

            in this snippet of the code you can see how the nesting functions when you click into the host function, a nested NAV bar is created with Dashboard,income, vans and reviews. with in this you can actually see that the vans nests even further creating routes within that section for details, pricing and photos. so this is a nest with in a nest allowing all other NAV bars to remain on the page with out requiring a full reload

            The nested routes under it (e.g., Dashboard, Income, Vans) are rendered within an <Outlet> component, allowing the parent route to stay in place while switching out the nested content.

### Question 3: Implementation of Navigation Controls and Dynamic Linking

**Key Points to Cover:**
- How does the `<Link>` component enhance navigation within a React application?
    the link component is what is used to navigate between the different routes with out causing the full page reload. for example when you click about, the /about route is pulled and only the necesary data is changed
- Describe the use of `NavLink` for active styling. What makes `NavLink` different from the basic `Link` component?
    navlink is an enhanced version of link, it automatically applies the active style to the link when it is active, this makes it easier to apply different styles when the link it active which is very helpful for navigation menus and user comfort (easier to see where you are)
- Discuss the use of search parameters and the `useSearchParams` hook to dynamically filter content, as seen in the VanLife project challenges.
    The useSearchParams hook is part of React Router's API, and it allows you to read and modify the query string of the URL. The query string is the part of the URL that comes after the ?, which is typically used to pass parameters in the URL.
        for example 
            A URL like /vans?type=luxury contains a query parameter type with the value luxury.
           The useSearchParams hook allows you to read the value of this parameter and use it in your component.  
           const typeFilter = searchParams.get("type");
           so it will pull luxury if that is what has already been filtering, and is then used to ensure that the filtering remains when it is being navigated through the code

Be prepared to provide code snippets and real-world application examples from your Van Life Project to support your explanations.

Make sure to submit your project to the DJS08 Project Tab on the LMS. Include a link to your Loom Presentation in your README.
