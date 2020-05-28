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
# <a name="store-asymmetric-keys-in-a-key-container"></a><span data-ttu-id="2f8ca-102">키 컨테이너에 비대칭 키 저장</span><span class="sxs-lookup"><span data-stu-id="2f8ca-102">Store asymmetric keys in a key container</span></span>

<span data-ttu-id="2f8ca-103">비대칭 프라이빗 키는 로컬 컴퓨터에 축자로 저장하거나 일반 텍스트로 저장해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f8ca-103">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="2f8ca-104">개인 키를 저장 해야 하는 경우 키 컨테이너를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8ca-104">If you need to store a private key, use a key container.</span></span> <span data-ttu-id="2f8ca-105">키 컨테이너에 대 한 자세한 내용은 [컴퓨터 수준 및 사용자 수준 RSA 키 컨테이너 이해](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2f8ca-105">For more information on key containers, see [Understanding machine-level and user-level RSA key containers](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100)).</span></span>

## <a name="create-an-asymmetric-key-and-save-it-in-a-key-container"></a><span data-ttu-id="2f8ca-106">비대칭 키를 만들어 키 컨테이너에 저장</span><span class="sxs-lookup"><span data-stu-id="2f8ca-106">Create an asymmetric key and save it in a key container</span></span>

1. <span data-ttu-id="2f8ca-107">클래스의 새 인스턴스를 만들고 <xref:System.Security.Cryptography.CspParameters> 키 컨테이너를 호출 하려는 이름을 필드에 전달 합니다 <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="2f8ca-107">Create a new instance of a <xref:System.Security.Cryptography.CspParameters> class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>

1. <span data-ttu-id="2f8ca-108">클래스에서 파생 되는 클래스의 새 인스턴스를 만들고 <xref:System.Security.Cryptography.AsymmetricAlgorithm> (일반적으로 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 또는 <xref:System.Security.Cryptography.DSACryptoServiceProvider> ) 이전에 만든 개체를 `CspParameters` 해당 생성자에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8ca-108">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually <xref:System.Security.Cryptography.RSACryptoServiceProvider> or <xref:System.Security.Cryptography.DSACryptoServiceProvider>) and pass the previously created `CspParameters` object to its constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="2f8ca-109">비대칭 키의 생성 및 검색은 한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="2f8ca-109">The creation and retrieval of an asymmetric key is one operation.</span></span> <span data-ttu-id="2f8ca-110">키가 아직 컨테이너에 없는 경우 반환 되기 전에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="2f8ca-110">If a key is not already in the container, it's created before being returned.</span></span>
>
> - <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType>
> - <xref:System.Security.Cryptography.DSA.ToXmlString%2A?displayProperty=nameWithType>

## <a name="delete-the-key-from-the-key-container"></a><span data-ttu-id="2f8ca-111">키 컨테이너에서 키를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8ca-111">Delete the key from the key container</span></span>

1. <span data-ttu-id="2f8ca-112">클래스의 새 인스턴스를 만들고 `CspParameters` 키 컨테이너를 호출 하려는 이름을 필드에 전달 합니다 <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="2f8ca-112">Create a new instance of a `CspParameters` class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>

1. <span data-ttu-id="2f8ca-113">클래스에서 파생 되는 클래스의 새 인스턴스를 만들고 <xref:System.Security.Cryptography.AsymmetricAlgorithm> (일반적으로 `RSACryptoServiceProvider` 또는 `DSACryptoServiceProvider` ) 이전에 만든 개체를 `CspParameters` 해당 생성자에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8ca-113">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually `RSACryptoServiceProvider` or `DSACryptoServiceProvider`) and pass the previously created `CspParameters` object to its constructor.</span></span>

1. <span data-ttu-id="2f8ca-114"><xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> 에서 파생 되는 클래스의 또는 속성 `AsymmetricAlgorithm` `false` (Visual Basic)을로 `False` 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8ca-114">Set the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> or the <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> property of the class that derives from `AsymmetricAlgorithm` to `false` (`False` in Visual Basic).</span></span>

1. <span data-ttu-id="2f8ca-115">`Clear`에서 파생 되는 클래스의 메서드를 호출 `AsymmetricAlgorithm` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8ca-115">Call the `Clear` method of the class that derives from `AsymmetricAlgorithm`.</span></span> <span data-ttu-id="2f8ca-116">이 메서드는 클래스의 모든 리소스를 해제하고 키 컨테이너를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="2f8ca-116">This method releases all resources of the class and clears the key container.</span></span>

## <a name="example"></a><span data-ttu-id="2f8ca-117">예제</span><span class="sxs-lookup"><span data-stu-id="2f8ca-117">Example</span></span>

<span data-ttu-id="2f8ca-118">다음 예제에서는 비대칭 키를 만들어 키 컨테이너에 저장하고 나중에 키를 검색하며 컨테이너에서 키를 삭제하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f8ca-118">The following example demonstrates how to create an asymmetric key, save it in a key container, retrieve the key at a later time, and delete the key from the container.</span></span>

<span data-ttu-id="2f8ca-119">`GenKey_SaveInContainer` 메서드와 `GetKeyFromContainer` 메서드의 해당 코드는 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8ca-119">Notice that code in the `GenKey_SaveInContainer` method and the `GetKeyFromContainer` method is similar.</span></span> <span data-ttu-id="2f8ca-120">개체에 대 한 키 컨테이너 이름을 지정 하 <xref:System.Security.Cryptography.CspParameters> 고 <xref:System.Security.Cryptography.AsymmetricAlgorithm> <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> 속성이 나 <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> 속성이로 설정 된 개체에 전달 하는 경우 동작은 다음과 같습니다 `true` .</span><span class="sxs-lookup"><span data-stu-id="2f8ca-120">When you specify a key container name for a <xref:System.Security.Cryptography.CspParameters> object and pass it to an <xref:System.Security.Cryptography.AsymmetricAlgorithm> object with the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> property or <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> property set to `true`, the behavior is as follows:</span></span>

- <span data-ttu-id="2f8ca-121">지정된 이름의 키 컨테이너가 없는 경우 해당 이름의 키 컨테이너가 만들어지고 키가 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f8ca-121">If a key container with the specified name does not exist, then one is created and the key is persisted.</span></span>
- <span data-ttu-id="2f8ca-122">지정된 이름의 키 컨테이너가 있는 경우 컨테이너의 키가 현재 <xref:System.Security.Cryptography.AsymmetricAlgorithm> 개체에 자동으로 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f8ca-122">If a key container with the specified name does exist, then the key in the container is automatically loaded into the current <xref:System.Security.Cryptography.AsymmetricAlgorithm> object.</span></span>

<span data-ttu-id="2f8ca-123">따라서 메서드의 코드는 첫 번째로 `GenKey_SaveInContainer` 실행 되기 때문에 키를 유지 하 고, 메서드의 코드는 `GetKeyFromContainer` 두 번째로 실행 되었기 때문에 키를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f8ca-123">Therefore, the code in the `GenKey_SaveInContainer` method persists the key because it is run first, while the code in the `GetKeyFromContainer` method loads the key because it's run second.</span></span>

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

<span data-ttu-id="2f8ca-124">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2f8ca-124">The output is as follows:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2f8ca-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f8ca-125">See also</span></span>

- [<span data-ttu-id="2f8ca-126">암호화 및 암호 해독을 위한 키 생성</span><span class="sxs-lookup"><span data-stu-id="2f8ca-126">Generating keys for encryption and decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="2f8ca-127">데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="2f8ca-127">Encrypting data</span></span>](encrypting-data.md)
- [<span data-ttu-id="2f8ca-128">데이터 암호 해독</span><span class="sxs-lookup"><span data-stu-id="2f8ca-128">Decrypting data</span></span>](decrypting-data.md)
- [<span data-ttu-id="2f8ca-129">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="2f8ca-129">Cryptographic services</span></span>](cryptographic-services.md)
