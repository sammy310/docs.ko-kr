---
title: Assert 메서드 사용
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- granting permissions, overriding security checks
- code access security, overriding security checks
- overriding security checks
- security [.NET Framework], overriding security checks
- security [.NET Framework], assertions
- asserted permissions
- Assert method
- caller security checks
- permissions [.NET Framework], overriding security checks
- permissions [.NET Framework], assertions
ms.assetid: 1e40f4d3-fb7d-4f19-b334-b6076d469ea9
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9634370b0031ac2e19ab5b357d7e9da5a5dcea1c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64639847"
---
# <a name="using-the-assert-method"></a><span data-ttu-id="03fdd-102">Assert 메서드 사용</span><span class="sxs-lookup"><span data-stu-id="03fdd-102">Using the Assert Method</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="03fdd-103"><xref:System.Security.CodeAccessPermission.Assert%2A>는 코드 액세스 권한 클래스 및 <xref:System.Security.PermissionSet> 클래스에서 호출할 수 있는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-103"><xref:System.Security.CodeAccessPermission.Assert%2A> is a method that can be called on code access permission classes and on the <xref:System.Security.PermissionSet> class.</span></span> <span data-ttu-id="03fdd-104">사용할 수 있습니다 **Assert** 수행 작업을 수행할 수 있는 권한이 코드의 호출자가 코드 (및 다운스트림 호출자)를 사용 하도록 설정 하려면 없을 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-104">You can use **Assert** to enable your code (and downstream callers) to perform actions that your code has permission to do but its callers might not have permission to do.</span></span> <span data-ttu-id="03fdd-105">보안 어설션은 보안 검사 중 런타임이 수행하는 일반적인 프로세스를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-105">A security assertion changes the normal process that the runtime performs during a security check.</span></span> <span data-ttu-id="03fdd-106">사용 권한을 어설션하는 경우 어설션된 권한에 대해 코드의 호출자를 검사하지 않도록 보안 시스템에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-106">When you assert a permission, it tells the security system not to check the callers of your code for the asserted permission.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="03fdd-107">어설션은 보안 허점을 열고 보안 제한을 적용하는 런타임 메커니즘을 저해할 수 있으므로 신중하게 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-107">Use assertions carefully because they can open security holes and undermine the runtime's mechanism for enforcing security restrictions.</span></span>  
  
 <span data-ttu-id="03fdd-108">어설션은 라이브러리가 비관리 코드를 호출하거나 라이브러리의 의도한 용도와 명확한 관련이 없는 권한이 필요한 호출을 수행하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-108">Assertions are useful in situations in which a library calls into unmanaged code or makes a call that requires a permission that is not obviously related to the library's intended use.</span></span> <span data-ttu-id="03fdd-109">모든 비관리 코드를 호출 해야 하는 코드에 관리 되는 예를 들어 **SecurityPermission** 사용 하 여 합니다 **UnmanagedCode** 플래그를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-109">For example, all managed code that calls into unmanaged code must have **SecurityPermission** with the **UnmanagedCode** flag specified.</span></span> <span data-ttu-id="03fdd-110">로컬 인트라넷에서 다운로드된 코드와 같은, 로컬 컴퓨터에서 시작되지 않은 코드에는 기본적으로 이 사용 권한이 부여되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-110">Code that does not originate from the local computer, such as code that is downloaded from the local intranet, will not be granted this permission by default.</span></span> <span data-ttu-id="03fdd-111">따라서 로컬 인트라넷에서 다운로드된 코드가 비관리 코드를 사용하는 라이브러리를 호출할 수 있으려면 라이브러리에서 어설션된 사용 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-111">Therefore, in order for code that is downloaded from the local intranet to be able to call a library that uses unmanaged code, it must have the permission asserted by the library.</span></span> <span data-ttu-id="03fdd-112">또한 일부 라이브러리는 호출자에게 표시되지 않으며 특별한 사용 권한이 필요한 호출을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-112">Additionally, some libraries might make calls that are unseen to callers and require special permissions.</span></span>  
  
 <span data-ttu-id="03fdd-113">코드가 호출자로부터 완전히 숨겨지는 방식으로 리소스에 액세스하는 상황에서 어설션을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-113">You can also use assertions in situations in which your code accesses a resource in a way that is completely hidden from callers.</span></span> <span data-ttu-id="03fdd-114">예를 들어 라이브러리가 데이터베이스에서 정보를 얻지만 이 과정에서 컴퓨터 레지스트리의 정보도 읽는다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-114">For example, suppose your library acquires information from a database, but in the process also reads information from the computer registry.</span></span> <span data-ttu-id="03fdd-115">수 없으므로 해당 코드에 필요한 라이브러리를 사용 하는 개발자가 원본에 액세스할 수 없기 때문에 갖고 **RegistryPermission** 코드를 사용 하려면.</span><span class="sxs-lookup"><span data-stu-id="03fdd-115">Because developers using your library do not have access to your source, they have no way of knowing that their code requires **RegistryPermission** in order to use your code.</span></span> <span data-ttu-id="03fdd-116">이 경우 코드의 호출자에게 레지스트리에 액세스할 수 있는 권한을 요구하는 것이 타당하거나 필요하지 않다고 결정할 경우 레지스트리를 읽을 수 있는 권한을 어설션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-116">In this case, if you decide that it is not reasonable or necessary to require that callers of your code have permission to access the registry, you can assert permission for reading the registry.</span></span> <span data-ttu-id="03fdd-117">이 상황에서는 없는 호출자가 권한을 어설션하는 라이브러리에 대 한 적절 한 **RegistryPermission** 라이브러리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-117">In this situation, it is appropriate for the library to assert the permission so that callers without **RegistryPermission** can use the library.</span></span>  
  
 <span data-ttu-id="03fdd-118">어설션은 어설션된 권한 및 다운스트림 호출자가 요청한 권한이 동일한 형식이고 요청된 권한이 어설션된 권한의 하위 집합인 경우에만 스택 워크에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-118">The assertion affects the stack walk only if the asserted permission and a permission demanded by a downstream caller are of the same type and if the demanded permission is a subset of the asserted permission.</span></span> <span data-ttu-id="03fdd-119">예를 들어, 어설션 **FileIOPermission** 에 대 한 다운스트림 요청이 C 드라이브에 모든 파일을 읽을 **FileIOPermission** C:\Temp의 파일을 읽으려면 어설션이 영향을 줄 수는 스택 워크; 그러나 요청 된 경우 **FileIOPermission** C 드라이브에 쓸 어설션이 해도 아무런 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-119">For example, if you assert **FileIOPermission** to read all files on the C drive, and a downstream demand is made for **FileIOPermission** to read files in C:\Temp, the assertion could affect the stack walk; however, if the demand was for **FileIOPermission** to write to the C drive, the assertion would have no effect.</span></span>  
  
 <span data-ttu-id="03fdd-120">어설션을 수행하려면 코드에 어셜션하는 권한 및 어설션을 수행하는 권한을 나타내는 <xref:System.Security.Permissions.SecurityPermission>을 둘 다 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-120">To perform assertions, your code must be granted both the permission you are asserting and the <xref:System.Security.Permissions.SecurityPermission> that represents the right to make assertions.</span></span> <span data-ttu-id="03fdd-121">코드에 부여되지 않은 권한을 어설션할 수도 있지만 어설션을 통해 보안 검사가 성공하기 전에 실패하므로 어설션의 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-121">Although you could assert a permission that your code has not been granted, the assertion would be pointless because the security check would fail before the assertion could cause it to succeed.</span></span>  
  
 <span data-ttu-id="03fdd-122">다음 그림에서는 사용 하는 경우 어떻게 되는지 보여 줍니다 **Assert**합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-122">The following illustration shows what happens when you use **Assert**.</span></span> <span data-ttu-id="03fdd-123">다음 문이 A, B, C, E 및 F 어셈블리와 두 개의 사용 권한 P1과 P1A에 대해 true라고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-123">Assume that the following statements are true about assemblies A, B, C, E, and F, and two permissions, P1 and P1A:</span></span>  
  
- <span data-ttu-id="03fdd-124">P1A는 C 드라이브의 .txt 파일을 읽을 수 있는 권한을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-124">P1A represents the right to read .txt files on the C drive.</span></span>  
  
- <span data-ttu-id="03fdd-125">P1은 C 드라이브의 모든 파일을 읽을 수 있는 권한을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-125">P1 represents the right to read all files on the C drive.</span></span>  
  
- <span data-ttu-id="03fdd-126">P1A와 P1은 둘 다 **FileIOPermission** 형식이 고 P1A는 P1의 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-126">P1A and P1 are both **FileIOPermission** types, and P1A is a subset of P1.</span></span>  
  
- <span data-ttu-id="03fdd-127">어셈블리 E와 F에는 P1A 권한이 부여되었습니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-127">Assemblies E and F have been granted P1A permission.</span></span>  
  
- <span data-ttu-id="03fdd-128">어셈블리 C에는 P1 권한이 부여되었습니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-128">Assembly C has been granted P1 permission.</span></span>  
  
- <span data-ttu-id="03fdd-129">어셈블리 A와 B에는 P1 및 P1A 권한이 부여되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-129">Assemblies A and B have been granted neither P1 nor P1A permissions.</span></span>  
  
- <span data-ttu-id="03fdd-130">메서드 A는 어셈블리 A에 포함되고, 메서드 B는 어셈블리 B에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-130">Method A is contained in assembly A, method B is contained in assembly B, and so on.</span></span>  
  
 ![Assert 메서드 어셈블리를 보여 주는 다이어그램입니다.](./media/using-the-assert-method/assert-method-assemblies.gif)    
  
 <span data-ttu-id="03fdd-132">이 시나리오, 메서드는 호출 B, C B 호출, C 호출 E, E 호출에서는 F 어설션 (사용 권한 P1) C 드라이브에 파일을 읽을 수 있는 권한 및 E 메서드 (권한 P1A) C 드라이브의.txt 파일을 읽을 권한을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-132">In this scenario, method A calls B, B calls C, C calls E, and E calls F. Method C asserts permission to read files on the C drive (permission P1), and method E demands permission to read .txt files on the C drive (permission P1A).</span></span> <span data-ttu-id="03fdd-133">F의 요청이 런타임에 발생 하면 f의 모든 호출자의 권한을 검사 하는 스택 워크가 수행 되어 E부터 시작 부여한 P1A 권한이 하므로 C의 어설션이 발견 된 위치만 C의 권한을 확인 하려면 스택 워크가 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-133">When the demand in F is encountered at run time, a stack walk is performed to check the permissions of all callers of F, starting with E. E has been granted P1A permission, so the stack walk proceeds to examine the permissions of C, where C's assertion is discovered.</span></span> <span data-ttu-id="03fdd-134">요청된 권한(P1A)이 어설션된 권한(P1)의 하위 집합이기 때문에 스택 워크가 중지되고 보안 검사가 자동으로 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-134">Because the demanded permission (P1A) is a subset of the asserted permission (P1), the stack walk stops and the security check automatically succeeds.</span></span> <span data-ttu-id="03fdd-135">어셈블리 A와 B에 권한 P1A가 부여되지 않은 것은 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-135">It does not matter that assemblies A and B have not been granted permission P1A.</span></span> <span data-ttu-id="03fdd-136">P1을 어설션하여 메서드 C는 호출자에게 리소스에 액세스할 수 있는 권한이 부여되지 않은 경우에도 호출자가 P1로 보호된 리소스에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-136">By asserting P1, method C ensures that its callers can access the resource protected by P1, even if the callers have not been granted permission to access that resource.</span></span>  
  
 <span data-ttu-id="03fdd-137">클래스 라이브러리를 디자인하고 클래스가 보호된 리소스에 액세스하는 경우 대체로 클래스의 호출자에게 적절한 권한을 요구하는 보안 요청을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-137">If you design a class library and a class accesses a protected resource, you should, in most cases, make a security demand requiring that the callers of the class have the appropriate permission.</span></span> <span data-ttu-id="03fdd-138">클래스는 다음 작업을 수행 하는 경우 해당 호출자의 대부분을 알고 있는 권한이 없으며 코드를 호출할 수 있게 하는 것에 대 한 책임을 져야 감수 하려는 경우에 호출 하 여 권한을 어설션할 수 있습니다는 **Assert** 작업을 나타내는 권한 개체에서 메서드 코드를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-138">If the class then performs an operation for which you know most of its callers will not have permission, and if you are willing to take the responsibility for letting these callers call your code, you can assert the permission by calling the **Assert** method on a permission object that represents the operation the code is performing.</span></span> <span data-ttu-id="03fdd-139">사용 하 여 **Assert** 수 없는 호출자가 일반적으로 수 있도록이 방식으로 코드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-139">Using **Assert** in this way lets callers that normally could not do so call your code.</span></span> <span data-ttu-id="03fdd-140">따라서 권한을 어설션하는 경우 구성 요소가 잘못 사용되지 않도록 사전에 적절한 보안 검사를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-140">Therefore, if you assert a permission, you should be sure to perform appropriate security checks beforehand to prevent your component from being misused.</span></span>  
  
 <span data-ttu-id="03fdd-141">예를 들어 신뢰할 수 있는 라이브러리 클래스에 파일을 삭제하는 메서드가 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-141">For example, suppose your highly trusted library class has a method that deletes files.</span></span> <span data-ttu-id="03fdd-142">관리되지 않은 Win32 함수를 호출하여 파일에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-142">It accesses the file by calling an unmanaged Win32 function.</span></span> <span data-ttu-id="03fdd-143">코드를 호출 하는 호출자 **삭제** 삭제할 파일의 이름을 전달 하는 메서드, C:\Test.txt 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-143">A caller invokes your code's **Delete** method, passing in the name of the file to be deleted, C:\Test.txt.</span></span> <span data-ttu-id="03fdd-144">내 합니다 **삭제** 메서드를 작성 하는 코드는 <xref:System.Security.Permissions.FileIOPermission> C:\Test.txt에 대 한 쓰기 액세스를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-144">Within the **Delete** method, your code creates a <xref:System.Security.Permissions.FileIOPermission> object representing write access to C:\Test.txt.</span></span> <span data-ttu-id="03fdd-145">파일을 삭제하려면 쓰기 권한이 필요합니다. 다음 코드를 호출 하 여 명령적 보안 검사를 호출 합니다 **FileIOPermission** 개체의 **수요** 메서드.</span><span class="sxs-lookup"><span data-stu-id="03fdd-145">(Write access is required to delete a file.) Your code then invokes an imperative security check by calling the **FileIOPermission** object's **Demand** method.</span></span> <span data-ttu-id="03fdd-146">호출 스택의 호출자 중 하나에 이 권한이 없는 경우 <xref:System.Security.SecurityException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-146">If one of the callers in the call stack does not have this permission, a <xref:System.Security.SecurityException> is thrown.</span></span> <span data-ttu-id="03fdd-147">예외가 발생하지 않으면 모든 호출자에게 C:\Test.txt에 액세스할 수 있는 권한이 있음을 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-147">If no exception is thrown, you know that all callers have the right to access C:\Test.txt.</span></span> <span data-ttu-id="03fdd-148">대부분의 호출자에 게 비관리 코드에 액세스할 권한이 없는를 만들고 생각 하므로 코드를 <xref:System.Security.Permissions.SecurityPermission> 개체의 호출을 비관리 코드를 호출할 수 있는 권한을 나타내는 개체 **Assert** 메서드.</span><span class="sxs-lookup"><span data-stu-id="03fdd-148">Because you believe that most of your callers will not have permission to access unmanaged code, your code then creates a <xref:System.Security.Permissions.SecurityPermission> object that represents the right to call unmanaged code and calls the object's **Assert** method.</span></span> <span data-ttu-id="03fdd-149">끝으로, 관리되지 않는 Win32 함수를 호출하여 C:\Text.txt를 삭제하고 호출자에게 컨트롤을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-149">Finally, it calls the unmanaged Win32 function to delete C:\Text.txt and returns control to the caller.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="03fdd-150">다른 코드가 사용자 코드를 사용하여 어설션하는 권한으로 보호된 리소스를 액세스할 수 있는 상황에서는 코드에서 어설션을 사용하지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-150">You must be sure that your code does not use assertions in situations where your code can be used by other code to access a resource that is protected by the permission you are asserting.</span></span> <span data-ttu-id="03fdd-151">예를 들어 호출자가 매개 변수로 이름이 지정 된 파일에 기록 하는 코드에서를 어설션 하지 않습니다는 **FileIOPermission** 쓰기용으로 파일에 코드를 타사에 의해 악용 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-151">For example, in code that writes to a file whose name is specified by the caller as a parameter, you would not assert the **FileIOPermission** for writing to files because your code would be open to misuse by a third party.</span></span>  
  
 <span data-ttu-id="03fdd-152">명령적 보안 구문을 사용 하면 호출 된 **Assert** 동일한 메서드의 여러 권한에 대해는 메서드를 사용 하면 보안 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-152">When you use the imperative security syntax, calling the **Assert** method on multiple permissions in the same method causes a security exception to be thrown.</span></span> <span data-ttu-id="03fdd-153">대신 만들어야를 **PermissionSet** 개체, 호출 및 호출 하려는 개별 권한을 전달 합니다 **Assert** 메서드를 **PermissionSet** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-153">Instead, you should create a **PermissionSet** object, pass it the individual permissions you want to invoke, and then call the **Assert** method on the **PermissionSet** object.</span></span> <span data-ttu-id="03fdd-154">호출할 수 있습니다 합니다 **Assert** 메서드 선언적 보안 구문을 사용 하면 한 번 이상.</span><span class="sxs-lookup"><span data-stu-id="03fdd-154">You can call the **Assert** method more than once when you use the declarative security syntax.</span></span>  
  
 <span data-ttu-id="03fdd-155">다음 예제에서는 재정의 보안 검사를 사용 하 여 선언적 구문을 보여 줍니다 합니다 **Assert** 메서드.</span><span class="sxs-lookup"><span data-stu-id="03fdd-155">The following example shows declarative syntax for overriding security checks using the **Assert** method.</span></span> <span data-ttu-id="03fdd-156">있음을 합니다 **FileIOPermissionAttribute** 두 값을 사용 하는 구문:는 <xref:System.Security.Permissions.SecurityAction> 열거형과 권한이 부여 되는 디렉터리나 파일의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-156">Notice that the **FileIOPermissionAttribute** syntax takes two values: a <xref:System.Security.Permissions.SecurityAction> enumeration and the location of the file or directory to which permission is to be granted.</span></span> <span data-ttu-id="03fdd-157">에 대 한 호출 **Assert** 에 대 한 액세스에 대 한 요청이 `C:\Log.txt` 파일에 액세스할 수 있는 권한이 호출자에 게 확인 하지 않습니다 하는 경우에 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-157">The call to **Assert** causes demands for access to `C:\Log.txt` to succeed, even though callers are not checked for permission to access the file.</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.IO  
Imports System.Security.Permissions  
  
Namespace LogUtil  
   Public Class Log  
      Public Sub New()  
  
      End Sub  
  
     <FileIOPermission(SecurityAction.Assert, All := "C:\Log.txt")> Public Sub   
      MakeLog()  
         Dim TextStream As New StreamWriter("C:\Log.txt")  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now) '  
         TextStream.Close()  
      End Sub  
   End Class  
End Namespace  
```  
  
```csharp  
namespace LogUtil  
{  
   using System;  
   using System.IO;  
   using System.Security.Permissions;  
  
   public class Log  
   {  
      public Log()  
      {      
      }     
      [FileIOPermission(SecurityAction.Assert, All = @"C:\Log.txt")]  
      public void MakeLog()  
      {     
         StreamWriter TextStream = new StreamWriter(@"C:\Log.txt");  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now);  
         TextStream.Close();  
      }  
   }  
}   
```  
  
 <span data-ttu-id="03fdd-158">보안 검사를 재정의 사용 하 여 다음 코드 조각은 명령적 구문을 보여 줍니다 합니다 **Assert** 메서드.</span><span class="sxs-lookup"><span data-stu-id="03fdd-158">The following code fragments show imperative syntax for overriding security checks using the **Assert** method.</span></span> <span data-ttu-id="03fdd-159">이 예제에서는 인스턴스를 **FileIOPermission** 개체 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-159">In this example, an instance of the **FileIOPermission** object is declared.</span></span> <span data-ttu-id="03fdd-160">해당 생성자에 전달 됩니다 **FileIOPermissionAccess.AllAccess** 다음 파일의 위치를 설명 하는 문자열에 허용 되는 액세스 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-160">Its constructor is passed **FileIOPermissionAccess.AllAccess** to define the type of access allowed, followed by a string describing the file's location.</span></span> <span data-ttu-id="03fdd-161">한 번 합니다 **FileIOPermission** 개체를 정의 호출 하기만 하면 해당 **Assert** 보안 검사를 재정의 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="03fdd-161">Once the **FileIOPermission** object is defined, you only need to call its **Assert** method to override the security check.</span></span>  
  
```vb  
Option Explicit  
Option Strict  
Imports System  
Imports System.IO  
Imports System.Security.Permissions  
Namespace LogUtil  
   Public Class Log  
      Public Sub New()  
      End Sub 'New  
  
      Public Sub MakeLog()  
         Dim FilePermission As New FileIOPermission(FileIOPermissionAccess.AllAccess, "C:\Log.txt")  
         FilePermission.Assert()  
         Dim TextStream As New StreamWriter("C:\Log.txt")  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now)  
         TextStream.Close()  
      End Sub  
   End Class  
End Namespace  
```  
  
```csharp  
namespace LogUtil  
{  
   using System;  
   using System.IO;  
   using System.Security.Permissions;  
  
   public class Log  
   {  
      public Log()  
      {      
      }     
      public void MakeLog()  
      {  
         FileIOPermission FilePermission = new FileIOPermission(FileIOPermissionAccess.AllAccess,@"C:\Log.txt");   
         FilePermission.Assert();  
         StreamWriter TextStream = new StreamWriter(@"C:\Log.txt");  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now);  
         TextStream.Close();  
      }  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="03fdd-162">참고자료</span><span class="sxs-lookup"><span data-stu-id="03fdd-162">See also</span></span>

- <xref:System.Security.PermissionSet>
- <xref:System.Security.Permissions.SecurityPermission>
- <xref:System.Security.Permissions.FileIOPermission>
- <xref:System.Security.Permissions.SecurityAction>
- [<span data-ttu-id="03fdd-163">특성</span><span class="sxs-lookup"><span data-stu-id="03fdd-163">Attributes</span></span>](../../../docs/standard/attributes/index.md)
- [<span data-ttu-id="03fdd-164">코드 액세스 보안</span><span class="sxs-lookup"><span data-stu-id="03fdd-164">Code Access Security</span></span>](../../../docs/framework/misc/code-access-security.md)
