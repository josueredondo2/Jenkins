withCredentials([usernamePassword(credentialsId: 'jenkins-api',
                                  usernameVariable: 'JENKINS_USER',
                                  passwordVariable: 'JENKINS_TOKEN')]) {
    powershell '''
        $jenkinsUrl = "http://localhost:9090"

        $pair = "$env:JENKINS_USER:$env:JENKINS_TOKEN"
        $encodedCreds = [Convert]::ToBase64String([Text.Encoding]::ASCII.GetBytes($pair))

        $response = Invoke-RestMethod -Uri "$jenkinsUrl/computer/api/json" -Headers @{ Authorization = "Basic $encodedCreds" }

        $response.computer | Where-Object { $_.displayName -ne "Built-In Node" } |
            ForEach-Object {
                Write-Output "Nodo: $($_.displayName) | Online: $($_.offline -eq $false)"
            }
    '''
}
