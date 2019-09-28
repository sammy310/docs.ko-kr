---
title: '방법: GenericPrincipal 및 GenericIdentity 개체 만들기'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Creating Generic Identity Objects
- GenericPrincipal Objects
- Creating GenericPrincipal Objects
- GenericIdentity Objects
ms.assetid: 465694cf-258b-4747-9dae-35b01a5bcdbb
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1f768242bffe619051779f87e950138ae9fcec6c
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353179"
---
# <a name="how-to-create-genericprincipal-and-genericidentity-objects"></a><span data-ttu-id="e2fcc-102">방법: GenericPrincipal 및 GenericIdentity 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="e2fcc-102">How to: Create GenericPrincipal and GenericIdentity Objects</span></span>

<span data-ttu-id="e2fcc-103">@No__t-0 클래스를 <xref:System.Security.Principal.GenericPrincipal> 클래스와 함께 사용 하 여 Windows 도메인과는 독립적으로 존재 하는 권한 부여 체계를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2fcc-103">You can use the <xref:System.Security.Principal.GenericIdentity> class in conjunction with the <xref:System.Security.Principal.GenericPrincipal> class to create an authorization scheme that exists independent of a Windows domain.</span></span>

### <a name="to-create-a-genericprincipal-object"></a><span data-ttu-id="e2fcc-104">GenericPrincipal 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e2fcc-104">To create a GenericPrincipal object</span></span>

1. <span data-ttu-id="e2fcc-105">identity 클래스의 새 인스턴스를 만들고, 유지하고 싶은 이름으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="e2fcc-105">Create a new instance of the identity class and initialize it with the name you want it to hold.</span></span> <span data-ttu-id="e2fcc-106">다음 코드에서는 새 **GenericIdentity** 개체를 만들고 이를 `MyUser`라는 이름으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="e2fcc-106">The following code creates a new **GenericIdentity** object and initializes it with the name `MyUser`.</span></span>

    ```vb
    Dim myIdentity As New GenericIdentity("MyUser")
    ```

    ```csharp
    GenericIdentity myIdentity = new GenericIdentity("MyUser");
    ```

2. <span data-ttu-id="e2fcc-107">**GenericPrincipal** 클래스의 새 인스턴스를 만들고 이를 이전에 만든 **GenericIdentity** 개체 및 해당 Principal에 연결할 역할을 나타내는 문자열 배열로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="e2fcc-107">Create a new instance of the **GenericPrincipal** class and initialize it with the previously created **GenericIdentity** object and an array of strings that represent the roles that you want associated with this principal.</span></span> <span data-ttu-id="e2fcc-108">다음의 코드 예제에서는 관리자 역할 및 사용자 역할을 나타내는 문자열 배열을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2fcc-108">The following code example specifies an array of strings that represent an administrator role and a user role.</span></span> <span data-ttu-id="e2fcc-109">이렇게 하면 앞의 **GenericIdentity** 및 문자열 배열을 사용하여 **GenericPrincipal**이 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2fcc-109">The **GenericPrincipal** is then initialized with the previous **GenericIdentity** and the string array.</span></span>

    ```vb
    Dim myStringArray As String() = {"Manager", "Teller"}
    DIm myPrincipal As New GenericPrincipal(myIdentity, myStringArray)
    ```

    ```csharp
    String[] myStringArray = {"Manager", "Teller"};
    GenericPrincipal myPrincipal = new GenericPrincipal(myIdentity, myStringArray);
    ```

3. <span data-ttu-id="e2fcc-110">해당 Principal을 현재 스레드에 연결하려면 다음 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e2fcc-110">Use the following code to attach the principal to the current thread.</span></span> <span data-ttu-id="e2fcc-111">이는 보안 주체가 여러 번 유효성을 검사 해야 하는 경우, 응용 프로그램에서 실행 되는 다른 코드에서 유효성을 검사 해야 하거나 <xref:System.Security.Permissions.PrincipalPermission> 개체에 의해 유효성을 검사 해야 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2fcc-111">This is valuable in situations where the principal must be validated several times, it must be validated by other code running in your application, or it must be validated by a <xref:System.Security.Permissions.PrincipalPermission> object.</span></span> <span data-ttu-id="e2fcc-112">Principal 개체를 스레드에 연결하지 않고도 이 개체에 대해 역할 기반 확인을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2fcc-112">You can still perform role-based validation on the principal object without attaching it to the thread.</span></span> <span data-ttu-id="e2fcc-113">자세한 내용은 [Principal 개체 바꾸기](../../../docs/standard/security/replacing-a-principal-object.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2fcc-113">For more information, see [Replacing a Principal Object](../../../docs/standard/security/replacing-a-principal-object.md).</span></span>

    ```vb
    Thread.CurrentPrincipal = myPrincipal
    ```

    ```csharp
    Thread.CurrentPrincipal = myPrincipal;
    ```

## <a name="example"></a><span data-ttu-id="e2fcc-114">예제</span><span class="sxs-lookup"><span data-stu-id="e2fcc-114">Example</span></span>

<span data-ttu-id="e2fcc-115">다음 코드 예제에서는 **GenericPrincipal** 및 **GenericIdentity**의 인스턴스를 만드는 방법을 보여 줍니다</span><span class="sxs-lookup"><span data-stu-id="e2fcc-115">The following code example demonstrates how to create an instance of a **GenericPrincipal** and a **GenericIdentity**.</span></span> <span data-ttu-id="e2fcc-116">이 코드에서는 해당 개체의 값을 콘솔에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e2fcc-116">This code displays the values of these objects to the console.</span></span>

```vb
Imports System
Imports System.Security.Principal
Imports System.Threading

Public Class Class1

    Public Shared Sub Main()
        ' Create generic identity.
        Dim myIdentity As New GenericIdentity("MyIdentity")

        ' Create generic principal.
        Dim myStringArray As String() =  {"Manager", "Teller"}
        Dim myPrincipal As New GenericPrincipal(myIdentity, myStringArray)

        ' Attach the principal to the current thread.
        ' This is not required unless repeated validation must occur,
        ' other code in your application must validate, or the
        ' PrincipalPermission object is used.
        Thread.CurrentPrincipal = myPrincipal

        ' Print values to the console.
        Dim name As String = myPrincipal.Identity.Name
        Dim auth As Boolean = myPrincipal.Identity.IsAuthenticated
        Dim isInRole As Boolean = myPrincipal.IsInRole("Manager")

        Console.WriteLine("The name is: {0}", name)
        Console.WriteLine("The isAuthenticated is: {0}", auth)
        Console.WriteLine("Is this a Manager? {0}", isInRole)

    End Sub

End Class
```

```csharp
using System;
using System.Security.Principal;
using System.Threading;

public class Class1
{
    public static int Main(string[] args)
    {
    // Create generic identity.
    GenericIdentity myIdentity = new GenericIdentity("MyIdentity");

    // Create generic principal.
    String[] myStringArray = {"Manager", "Teller"};
    GenericPrincipal myPrincipal =
        new GenericPrincipal(myIdentity, myStringArray);

    // Attach the principal to the current thread.
    // This is not required unless repeated validation must occur,
    // other code in your application must validate, or the
    // PrincipalPermission object is used.
    Thread.CurrentPrincipal = myPrincipal;

    // Print values to the console.
    String name =  myPrincipal.Identity.Name;
    bool auth =  myPrincipal.Identity.IsAuthenticated;
    bool isInRole =  myPrincipal.IsInRole("Manager");

    Console.WriteLine("The name is: {0}", name);
    Console.WriteLine("The isAuthenticated is: {0}", auth);
    Console.WriteLine("Is this a Manager? {0}", isInRole);

    return 0;
    }
}
```

<span data-ttu-id="e2fcc-117">애플리케이션을 실행하면 다음과 같은 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2fcc-117">When executed, the application displays output similar to the following.</span></span>

```console
The Name is: MyIdentity
The IsAuthenticated is: True
Is this a Manager? True
```

## <a name="see-also"></a><span data-ttu-id="e2fcc-118">참조</span><span class="sxs-lookup"><span data-stu-id="e2fcc-118">See also</span></span>

- <xref:System.Security.Principal.GenericIdentity>
- <xref:System.Security.Principal.GenericPrincipal>
- <xref:System.Security.Permissions.PrincipalPermission>
- [<span data-ttu-id="e2fcc-119">Principal 개체 바꾸기</span><span class="sxs-lookup"><span data-stu-id="e2fcc-119">Replacing a Principal Object</span></span>](../../../docs/standard/security/replacing-a-principal-object.md)
- [<span data-ttu-id="e2fcc-120">Principal 개체 및 Identity 개체</span><span class="sxs-lookup"><span data-stu-id="e2fcc-120">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
