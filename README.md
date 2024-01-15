# K8s Learning

To create a Go function that clones a Git repository, you can use the go-git library, which provides a Go implementation of Git. You'll need to install this library first using go get:

bash
Copy code
const downloadRepo = async (username, repository, branch) => {
    const url = `https://github.com/${username}/${repository}/archive/${branch}.zip`;

    try {
        const response = await fetch(url);

        if (!response.ok) {
            throw new Error(`Failed to fetch repository: ${response.status} ${response.statusText}`);
        }

        // Create a write stream to save the ZIP archive
        const writeStream = fs.createWriteStream(`${repository}-${branch}.zip`);

        // Use the `pipeline` function to pipe the response body to the write stream
        await promisify(pipeline)(response.body, writeStream);

        console.log(`Repository cloned successfully as ${repository}-${branch}.zip`);
    } catch (error) {
        console.error('Error cloning repository:', error);
    }
};

// Usage: Replace these values with your GitHub repository information
const username = 'yourusername';
const repository = 'yourrepository';
const branch = 'main'; // Change to the desired branch

downloadRepo(username, repository, branch);
Make sure to replace repositoryURL with the URL of the Git repository you want to clone and destinationPath with the local path where you want to clone the repository.

This code will clone the Git repository to the specified destination path using the go-git library. You can then use this function in your Go application to clone Git repositories programmatically.





<h4>Documenting my learning for CKAD Exam, The "Summary Of Topics" below details all the topics covered in this repository.</h4>
<br>

![alt text](https://codefresh.io/wp-content/uploads/2017/02/Intro-to-Kubernetes-blog-b-2.png)<br>

<h2>Summary Of Topics</h2>
<h3>
    
[Configuration](https://github.com/EAS-Kalem/k8-learning/tree/main/Configuration) ✅
</h3>

```
- Enviroment Variables
    - Config Map 
    - Plain Key
    - Secrets
- Resource Requirements
- Security Contexts
- Service Accounts
- Taints and Tolerations
- Node Affinity
```
<h3>
    
[Multi Container Pods](https://github.com/EAS-Kalem/k8-learning/tree/main/Multi-Container%20Pods) ✅
</h3>


```
- Basics
```
<h3>

[Observability](https://github.com/EAS-Kalem/k8-learning/tree/main/Observability) ✅
</h3>

```
- Readiness Probe
    - Exec Command
    - HTTP Test
    - TCP Test
- Liveness Probe
- Logging
- Monitoring
```

<h3>
    
[Pod Design](https://github.com/EAS-Kalem/k8-learning/tree/main/POD%20Design) ✅
</h3>

```
- Labels, Selectors and Annotations
- Jobs
- Chron Jobs
```


<h3>

[Services & Networking](https://github.com/EAS-Kalem/k8-learning/tree/main/Services%20and%20Networking) 

</h3>

```
- Services
- Network Policies
```


<h3>

[State Persistence](https://github.com/EAS-Kalem/k8-learning/tree/main/State%20Persistence) 

</h3>

```
- Storage in Docker
- Volumes in Kubernetes
- Persistent Volumes
- Stateful Sets
```
Task Description
The goal of this task is to enhance the Continuous Integration and Continuous Deployment (CI/CD) process by consolidating two delta blocks into a single block. These delta blocks are currently part of the CI/CD pipeline for our onboarding applications. Merging these blocks will not only minimize the codebase but also reduce the potential for errors in future deployments.

Background
Our current CI/CD setup involves two separate delta blocks in the onboarding applications' pipeline. These blocks serve specific purposes but can be consolidated into a single block for improved maintainability and simplicity.

Objectives
Codebase Minimization: Merge the two existing delta blocks into a single block, reducing redundancy and improving code maintainability.
Error Prevention: By having a unified delta block, we aim to mitigate the risk of errors that may arise from managing two separate blocks.
Proposed Changes
Combine the logic from the existing delta blocks into a single delta block.
Update the CI/CD pipeline to use this consolidated delta block.
Ensure that the new configuration supports both onboarding applications seamlessly.
Benefits
Simplified Configuration: With a single delta block, configuration management becomes more straightforward.
Reduced Complexity: Minimizing the codebase reduces the complexity of the CI/CD process.
Error Resilience: Consolidating the blocks lowers the likelihood of configuration-related errors during deployment.
Testing Strategy
Unit Testing: Verify that the merged delta block functions as expected for each onboarding application.
Integration Testing: Ensure that the updated CI/CD pipeline integrates seamlessly with the rest of the deployment process.
End-to-End Testing: Validate the complete onboarding process with the consolidated delta block.
Rollback Plan
In the event of unforeseen issues, a rollback plan will be in place to revert the changes and restore the previous CI/CD configuration.

Documentation Updates
Update relevant documentation, including README files and developer guidelines, to reflect the changes made to the CI/CD process.

Additional Notes
Coordinate with team members involved in the deployment process to communicate the upcoming changes.
Schedule a deployment window that minimizes impact on ongoing development activities.
Acceptance Criteria
Successful execution of the consolidated delta block in the CI/CD pipeline.
No adverse impact on the functionality of the onboarding applications.
Documentation updated to reflect the changes made.
This task is expected to streamline our CI/CD pipeline, fostering a more efficient and error-resistant deployment process. Feel free to reach out if you have any questions or require further clarification.
