# Publish-SsoPasswordPolicy

## SYNOPSIS

Publish password policies for vCenter Single Sign-On.

## SYNTAX

### All-WorkloadDomains

```powershell
Publish-SsoPasswordPolicy -server <String> -user <String> -pass <String> -policy <String> [-allDomains]
 [-drift] [-reportPath <String>] [-policyFile <String>] [-json] [<CommonParameters>]
```

### Specific-WorkloadDomain

```powershell
Publish-SsoPasswordPolicy -server <String> -user <String> -pass <String> -policy <String>
 -workloadDomain <String> [-drift] [-reportPath <String>] [-policyFile <String>] [-json] [<CommonParameters>]
```

## DESCRIPTION

The Publish-SsoPasswordPolicy cmdlet retrieves the requested password policy for vCenter Single Sign-On and
converts the output to HTML.
The cmdlet connects to the SDDC Manager using the -server, -user, and -password values:

- Validates that network connectivity and authentication is possible to SDDC Manager
- Validates that network connectivity and authentication is possible to vCenter Server
- Retrieves the requested password policy for vCenter Single Sign-On and converts to HTML

## EXAMPLES

### EXAMPLE 1

```powershell
Publish-SsoPasswordPolicy -server sfo-vcf01.sfo.rainpole.io -user admin@local -pass VMw@re1!VMw@re1! -policy PasswordExpiration -allDomains
```

This example will return password expiration policy for vCenter Single Sign-On across all Workload Domains.

### EXAMPLE 2

```powershell
Publish-SsoPasswordPolicy -server sfo-vcf01.sfo.rainpole.io -user admin@local -pass VMw@re1!VMw@re1! -policy PasswordExpiration -workloadDomain sfo-w01
```

This example will return password expiration policy for vCenter Single Sign-On for a Workload Domain.

### EXAMPLE 3

```powershell
Publish-SsoPasswordPolicy -server sfo-vcf01.sfo.rainpole.io -user admin@local -pass VMw@re1!VMw@re1! -policy PasswordComplexity -allDomains
```

This example will return password complexity policy for vCenter Single Sign-On across all Workload Domains.

### EXAMPLE 4

```powershell
Publish-SsoPasswordPolicy -server sfo-vcf01.sfo.rainpole.io -user admin@local -pass VMw@re1!VMw@re1! -policy PasswordComplexity -workloadDomain sfo-w01
```

This example will return password complexity policy for vCenter Single Sign-On for a Workload Domain.

### EXAMPLE 5

```powershell
Publish-SsoPasswordPolicy -server sfo-vcf01.sfo.rainpole.io -user admin@local -pass VMw@re1!VMw@re1! -policy AccountLockout -allDomains
```

This example will return account lockout policy for vCenter Single Sign-On across all Workload Domains.

### EXAMPLE 6

```powershell
Publish-SsoPasswordPolicy -server sfo-vcf01.sfo.rainpole.io -user admin@local -pass VMw@re1!VMw@re1! -policy AccountLockout -workloadDomain sfo-w01
```

This example will return account lockout policy for vCenter Single Sign-On for a Workload Domain.

### EXAMPLE 7

```powershell
Publish-SsoPasswordPolicy -server sfo-vcf01.sfo.rainpole.io -user admin@local -pass VMw@re1!VMw@re1! -policy PasswordExpiration -workloadDomain sfo-m01 -drift -reportPath "F:\Reporting" -policyFile "passwordPolicyConfig.json"
```

This example will return password expiration policy for vCenter Single Sign-On across for a Workload Domains and compare the configuration against the passwordPolicyConfig.json.

## PARAMETERS

### -server

The fully qualified domain name of the SDDC Manager instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -user

The username to authenticate to the SDDC Manager instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -pass

The password to authenticate to the SDDC Manager instance.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -policy

The policy to publish.
One of: PasswordExpiration, PasswordComplexity, AccountLockout.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -allDomains

Switch to publish the policy for all workload domains.

```yaml
Type: SwitchParameter
Parameter Sets: All-WorkloadDomains
Aliases:

Required: True
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -workloadDomain

Switch to publish the policy for a specific workload domain.

```yaml
Type: String
Parameter Sets: Specific-WorkloadDomain
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -drift

Switch to compare the current configuration against the product defaults or a JSON file.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -reportPath

The path to save the policy report.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -policyFile

The path to the policy configuration file.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -json

Switch to publish the policy in JSON format.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### Common Parameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).
