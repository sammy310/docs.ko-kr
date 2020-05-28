---
title: '방법: 키 컨테이너에 비대칭 키 저장'
ms.date: 05/26/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET Framework], asymmetric keys
- storing asymmetric keys
- keys, asymmetric
- encryption keys
- keys, storing in key containers
- asymmetric keys [.NET Framework]
- encryption [.NET Framework], asymmetric keys
- decryption keys
ms.assetid: 0dbcbd8d-0dcf-40e9-9f0c-e3f162d35ccc
ms.openlocfilehash: 36bae05fbfb35dc112e0c543c9a1a975a8fa8db5
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/28/2020
ms.locfileid: "84143623"
---
# <a name="store-asymmetric-keys-in-a-key-container"></a>키 컨테이너에 비대칭 키 저장

비대칭 프라이빗 키는 로컬 컴퓨터에 축자로 저장하거나 일반 텍스트로 저장해서는 안 됩니다. 개인 키를 저장 해야 하는 경우 키 컨테이너를 사용 합니다. 키 컨테이너에 대 한 자세한 내용은 [컴퓨터 수준 및 사용자 수준 RSA 키 컨테이너 이해](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100))를 참조 하세요.

## <a name="create-an-asymmetric-key-and-save-it-in-a-key-container"></a>비대칭 키를 만들어 키 컨테이너에 저장

1. 클래스의 새 인스턴스를 만들고 <xref:System.Security.Cryptography.CspParameters> 키 컨테이너를 호출 하려는 이름을 필드에 전달 합니다 <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> .

1. 클래스에서 파생 되는 클래스의 새 인스턴스를 만들고 <xref:System.Security.Cryptography.AsymmetricAlgorithm> (일반적으로 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 또는 <xref:System.Security.Cryptography.DSACryptoServiceProvider> ) 이전에 만든 개체를 `CspParameters` 해당 생성자에 전달 합니다.

> [!NOTE]
> 비대칭 키의 생성 및 검색은 한 작업입니다. 키가 아직 컨테이너에 없는 경우 반환 되기 전에 만들어집니다.
>
> - <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType>
> - <xref:System.Security.Cryptography.DSA.ToXmlString%2A?displayProperty=nameWithType>

## <a name="delete-the-key-from-the-key-container"></a>키 컨테이너에서 키를 삭제 합니다.

1. 클래스의 새 인스턴스를 만들고 `CspParameters` 키 컨테이너를 호출 하려는 이름을 필드에 전달 합니다 <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> .

1. 클래스에서 파생 되는 클래스의 새 인스턴스를 만들고 <xref:System.Security.Cryptography.AsymmetricAlgorithm> (일반적으로 `RSACryptoServiceProvider` 또는 `DSACryptoServiceProvider` ) 이전에 만든 개체를 `CspParameters` 해당 생성자에 전달 합니다.

1. <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> 에서 파생 되는 클래스의 또는 속성 `AsymmetricAlgorithm` `false` (Visual Basic)을로 `False` 설정 합니다.

1. `Clear`에서 파생 되는 클래스의 메서드를 호출 `AsymmetricAlgorithm` 합니다. 이 메서드는 클래스의 모든 리소스를 해제하고 키 컨테이너를 지웁니다.

## <a name="example"></a>예제

다음 예제에서는 비대칭 키를 만들어 키 컨테이너에 저장하고 나중에 키를 검색하며 컨테이너에서 키를 삭제하는 방법을 보여 줍니다.

`GenKey_SaveInContainer` 메서드와 `GetKeyFromContainer` 메서드의 해당 코드는 유사합니다. 개체에 대 한 키 컨테이너 이름을 지정 하 <xref:System.Security.Cryptography.CspParameters> 고 <xref:System.Security.Cryptography.AsymmetricAlgorithm> <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> 속성이 나 <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> 속성이로 설정 된 개체에 전달 하는 경우 동작은 다음과 같습니다 `true` .

- 지정된 이름의 키 컨테이너가 없는 경우 해당 이름의 키 컨테이너가 만들어지고 키가 지속됩니다.
- 지정된 이름의 키 컨테이너가 있는 경우 컨테이너의 키가 현재 <xref:System.Security.Cryptography.AsymmetricAlgorithm> 개체에 자동으로 로드됩니다.

따라서 메서드의 코드는 첫 번째로 `GenKey_SaveInContainer` 실행 되기 때문에 키를 유지 하 고, 메서드의 코드는 `GetKeyFromContainer` 두 번째로 실행 되었기 때문에 키를 로드 합니다.

```vb
Imports System
Imports System.Security.Cryptography

Public Class StoreKey

    Public Shared Sub Main()
        Try
            ' Create a key and save it in a container.
            GenKey_SaveInContainer("MyKeyContainer")

            ' Retrieve the key from the container.
            GetKeyFromContainer("MyKeyContainer")

            ' Delete the key from the container.
            DeleteKeyFromContainer("MyKeyContainer")

            ' Create a key and save it in a container.
            GenKey_SaveInContainer("MyKeyContainer")

            ' Delete the key from the container.
            DeleteKeyFromContainer("MyKeyContainer")
        Catch e As CryptographicException
            Console.WriteLine(e.Message)
        End Try
    End Sub

    Private Shared Sub GenKey_SaveInContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        ' name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container MyKeyContainerName.
        Using rsa As New RSACryptoServiceProvider(parameters)
            ' Display the key information to the console.
            Console.WriteLine($"Key added to container:  {rsa.ToXmlString(True)}")
        End Using
    End Sub

    Private Shared Sub GetKeyFromContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        '  name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container MyKeyContainerName.
        Using rsa As New RSACryptoServiceProvider(parameters)
            ' Display the key information to the console.
            Console.WriteLine($"Key retrieved from container : {rsa.ToXmlString(True)}")
        End Using
    End Sub

    Private Shared Sub DeleteKeyFromContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        '  name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container.
        ' Delete the key entry in the container.
        Dim rsa As New RSACryptoServiceProvider(parameters) With {
            .PersistKeyInCsp = False
        }

        ' Call Clear to release resources and delete the key from the container.
        rsa.Clear()

        Console.WriteLine("Key deleted.")
    End Sub
End Class
```

```csharp
using System;
using System.Security.Cryptography;

public class StoreKey
{
    public static void Main()
    {
        try
        {
            // Create a key and save it in a container.
            GenKey_SaveInContainer("MyKeyContainer");

            // Retrieve the key from the container.
            GetKeyFromContainer("MyKeyContainer");

            // Delete the key from the container.
            DeleteKeyFromContainer("MyKeyContainer");

            // Create a key and save it in a container.
            GenKey_SaveInContainer("MyKeyContainer");

            // Delete the key from the container.
            DeleteKeyFromContainer("MyKeyContainer");
        }
        catch (CryptographicException e)
        {
            Console.WriteLine(e.Message);
        }
    }

    private static void GenKey_SaveInContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container MyKeyContainerName.
        using var rsa = new RSACryptoServiceProvider(parameters);

        // Display the key information to the console.
        Console.WriteLine($"Key added to container: \n  {rsa.ToXmlString(true)}");
    }

    private static void GetKeyFromContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container MyKeyContainerName.
        using var rsa = new RSACryptoServiceProvider(parameters);

        // Display the key information to the console.
        Console.WriteLine($"Key retrieved from container : \n {rsa.ToXmlString(true)}");
    }

    private static void DeleteKeyFromContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container.
        using var rsa = new RSACryptoServiceProvider(parameters)
        {
            // Delete the key entry in the container.
            PersistKeyInCsp = false
        };

        // Call Clear to release resources and delete the key from the container.
        rsa.Clear();

        Console.WriteLine("Key deleted.");
    }
}
```

출력은 다음과 같습니다.

```console
Key added to container:
<RSAKeyValue> Key Information A</RSAKeyValue>
Key retrieved from container :
<RSAKeyValue> Key Information A</RSAKeyValue>
Key deleted.
Key added to container:
<RSAKeyValue> Key Information B</RSAKeyValue>
Key deleted.
```

## <a name="see-also"></a>참고 항목

- [암호화 및 암호 해독을 위한 키 생성](generating-keys-for-encryption-and-decryption.md)
- [데이터 암호화](encrypting-data.md)
- [데이터 암호 해독](decrypting-data.md)
- [암호화 서비스](cryptographic-services.md)
