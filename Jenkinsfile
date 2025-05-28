// if this current jenkinsfile is in main branch , this CI job wont run 

@Library('Jenkins-Shared-Library-1') _  
// in jenkins console we mentioned this name along with the git repo url in the section of global pipeline libraries in manage jenkins --> system configuration. this will import the shared library and we can use the functions defined in the shared library
def configMap = [
    project: "expense",
    component: "backend"
    // we are passing the variables to all configMaps inside shared librray ; not only to nodeJSEKSPipeline(configMap)pipeline; since nodeJSEKSPipeline(configMap) is also a configMap, the values passed here will also get used in that since  we kept the same variables empty 
]
if (! env.BRANCH_NAME.equalsIgnoreCase('main')) {
    nodeJSEKSPipeline(configMap)
} 
else {
    echo "This is main branch, so skipping the pipeline"
    // we are not running the pipeline in main branch , main branch is used for production ONLY.
}