@Library('Jenkins-Shared-Library-1') _  
// in jenkins console we mentioned this name along with the git repo url in the section of global pipeline libraries in manage jenkins --> system configuration. this will import the shared library and we can use the functions defined in the shared library
def configMap = [
    project: "expense",
    component: "backend"
    // we are passing the variables to shared librray backend pipeline; in that file we kept the same variables empty since we are passing from here
]
if (! env.BRANCH_NAME.equalsIgnoreCase('main')) {
    nodeJSEKSPipeline(configMap)
} 
else {
    echo "This is main branch, so skipping the pipeline"
    // we are not running the pipeline in main branch , main branch is used for production ONLY.
}