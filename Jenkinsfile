powershell '''
    $jenkinsUrl = "http://localhost:9090/computer/api/json"
    $user = $env:JENKINS_USER
    $token = $env:JENKINS_TOKEN

    $result = curl.exe -s -u "$user:$token" $jenkinsUrl
    Write-Output $result
'''
