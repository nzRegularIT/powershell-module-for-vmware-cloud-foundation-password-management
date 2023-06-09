# Request-NsxtManagerAccountLockout

## SYNOPSIS

Retrieve account lockout policy for NSX Local Manager.

## SYNTAX

```powershell
Request-NsxtManagerAccountLockout -server <String> -user <String> -pass <String> -domain <String> [-drift]
 [-reportPath <String>] [-policyFile <String>] [<CommonParameters>]
```

## DESCRIPTION

The Request-NsxtManagerAccountLockout cmdlet retrieves the account lockout policy for each NSX Local Manager node for
a workload domain.
The cmdlet connects to SDDC Manager using the -server, -user, and -password values:

- Validates that network connectivity and authentication is possible to SDDC Manager
- Validates that network connectivity and authentication is possible to NSX Local Manager
- Retrieves the account lockpout policy

## EXAMPLES

### EXAMPLE 1

```powershell
Request-NsxtManagerAccountLockout -server sfo-vcf01.sfo.rainpole.io -user administrator@vsphere.local -pass VMw@re1! -domain sfo-m01
```

This example retrieves the account lockout policy for the NSX Local Manager nodes in sfo-m01 workload domain.

### EXAMPLE 2

```powershell
Request-NsxtManagerAccountLockout -server sfo-vcf01.sfo.rainpole.io -user administrator@vsphere.local -pass VMw@re1! -domain sfo-m01 -drift -reportPath "F:\Reporting" -policyFile "passwordPolicyConfig.json"
```

This example retrieves the account lockout policy for the NSX Local Manager nodes in sfo-m01 workload domain and checks the configuration drift using the provided configuration JSON.

### EXAMPLE 3

```powershell
Request-NsxtManagerAccountLockout -server sfo-vcf01.sfo.rainpole.io -user administrator@vsphere.local -pass VMw@re1! -domain sfo-m01 -drift
```

This example retrieves the account lockout policy for the NSX Local Manager nodes in sfo-m01 workload domain and compares the configuration against the product defaults.

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

### -domain

The name of the workload domain to retrieve the policy from.

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

### Common Parameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).