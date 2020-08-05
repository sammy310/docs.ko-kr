---
title: '방법: WindowsPrincipal 개체 만들기'
ms.date: 07/15/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsPrincipal objects, creating
- security [.NET], creating a WindowsPrincipal object
- security [.NET], principals
- principal objects, creating
ms.assetid: 56eb10ca-e61d-4ed2-af7a-555fc4c25a25
ms.openlocfilehash: d99d63dc766f37e7cc30888d2e77657595f909af
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557036"
---
# <a name="how-to-create-a-windowsprincipal-object"></a><span data-ttu-id="d6aee-102">방법: WindowsPrincipal 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="d6aee-102">How to: Create a WindowsPrincipal Object</span></span>

> [!NOTE]
> <span data-ttu-id="d6aee-103">이 문서는 Windows에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6aee-103">This article applies to Windows.</span></span>
>
> <span data-ttu-id="d6aee-104">ASP.NET Core에 대 한 자세한 내용은 [ASP.NET Core 보안](/aspnet/core/security/)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6aee-104">For information about ASP.NET Core, see [ASP.NET Core Security](/aspnet/core/security/).</span></span>

<span data-ttu-id="d6aee-105">코드에서 역할 기반 유효성 검사를 반복적으로 수행해야 하는지 또는 한 번만 수행해야 하는지에 따라 <xref:System.Security.Principal.WindowsPrincipal> 개체를 만드는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6aee-105">There are two ways to create a <xref:System.Security.Principal.WindowsPrincipal> object, depending on whether code must repeatedly perform role-based validation or must perform it only once.</span></span>  
  
<span data-ttu-id="d6aee-106">코드에서 역할 기반 유효성 검사를 반복적으로 수행해야 하는 경우 다음 절차 중 첫 번째 절차가 더 적은 오버헤드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d6aee-106">If code must repeatedly perform role-based validation, the first of the following procedures produces less overhead.</span></span> <span data-ttu-id="d6aee-107">코드에서 역할 기반 유효성 검사를 한 번만 수행해야 하는 경우 다음 절차 중 두 번째 절차를 사용하여 <xref:System.Security.Principal.WindowsPrincipal> 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6aee-107">When code needs to make role-based validations only once, you can create a <xref:System.Security.Principal.WindowsPrincipal> object by using the second of the following procedures.</span></span>  
  
### <a name="to-create-a-windowsprincipal-object-for-repeated-validation"></a><span data-ttu-id="d6aee-108">반복된 유효성 검사를 위한 WindowsPrincipal 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d6aee-108">To create a WindowsPrincipal object for repeated validation</span></span>  
  
1. <span data-ttu-id="d6aee-109">새 정책에 대한 요구 사항을 나타내는 <xref:System.Security.Principal.PrincipalPolicy> 열거형 값을 메서드에 전달하여 정적 <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> 속성에 의해서 반환된 <xref:System.AppDomain> 개체에서 <xref:System.AppDomain.SetPrincipalPolicy%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d6aee-109">Call the <xref:System.AppDomain.SetPrincipalPolicy%2A> method on the <xref:System.AppDomain> object that is returned by the static <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> property, passing the method a <xref:System.Security.Principal.PrincipalPolicy> enumeration value that indicates what the new policy should be.</span></span> <span data-ttu-id="d6aee-110">지원되는 값은 <xref:System.Security.Principal.PrincipalPolicy.NoPrincipal>, <xref:System.Security.Principal.PrincipalPolicy.UnauthenticatedPrincipal> 및 <xref:System.Security.Principal.PrincipalPolicy.WindowsPrincipal>입니다.</span><span class="sxs-lookup"><span data-stu-id="d6aee-110">Supported values are <xref:System.Security.Principal.PrincipalPolicy.NoPrincipal>, <xref:System.Security.Principal.PrincipalPolicy.UnauthenticatedPrincipal>, and <xref:System.Security.Principal.PrincipalPolicy.WindowsPrincipal>.</span></span> <span data-ttu-id="d6aee-111">다음 코드에서는 이 메서드 호출을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6aee-111">The following code demonstrates this method call.</span></span>  
  
    ```csharp  
    AppDomain.CurrentDomain.SetPrincipalPolicy(  
        PrincipalPolicy.WindowsPrincipal);  
    ```  
  
    ```vb  
    AppDomain.CurrentDomain.SetPrincipalPolicy( _  
        PrincipalPolicy.WindowsPrincipal)  
    ```  
  
2. <span data-ttu-id="d6aee-112">정책을 설정한 후 정적 <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> 속성을 사용하여 현재 Windows 사용자를 캡슐화하는 보안 주체를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d6aee-112">With the policy set, use the static <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> property to retrieve the principal that encapsulates the current Windows user.</span></span> <span data-ttu-id="d6aee-113">속성 반환 형식이 <xref:System.Security.Principal.IPrincipal>이므로 결과를 <xref:System.Security.Principal.WindowsPrincipal> 형식으로 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6aee-113">Because the property return type is <xref:System.Security.Principal.IPrincipal>, you must cast the result to a <xref:System.Security.Principal.WindowsPrincipal> type.</span></span> <span data-ttu-id="d6aee-114">다음 코드에서는 새 <xref:System.Security.Principal.WindowsPrincipal> 개체를 현재 스레드와 연결된 보안 주체의 값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="d6aee-114">The following code initializes a new <xref:System.Security.Principal.WindowsPrincipal> object to the value of the principal associated with the current thread.</span></span>  
  
    ```csharp  
    WindowsPrincipal myPrincipal =
        (WindowsPrincipal) Thread.CurrentPrincipal;  
    ```  
  
    ```vb  
    Dim myPrincipal As WindowsPrincipal = _  
        CType(Thread.CurrentPrincipal, WindowsPrincipal)
    ```  
  
3. <span data-ttu-id="d6aee-115">보안 주체 개체가 생성되면 여러 메서드 중 하나를 사용하여 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6aee-115">When the principal object has been created, you can use one of several methods to validate it.</span></span>  
  
### <a name="to-create-a-windowsprincipal-object-for-a-single-validation"></a><span data-ttu-id="d6aee-116">단일 유효성 검사를 위한 WindowsPrincipal 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d6aee-116">To create a WindowsPrincipal object for a single validation</span></span>  
  
1. <span data-ttu-id="d6aee-117">현재 Windows 계정을 쿼리하고 해당 계정에 대한 정보를 새로 만든 ID 개체에 배치하는 정적 <xref:System.Security.Principal.WindowsIdentity.GetCurrent%2A?displayProperty=nameWithType> 메서드를 호출하여 새 <xref:System.Security.Principal.WindowsIdentity> 개체를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="d6aee-117">Initialize a new <xref:System.Security.Principal.WindowsIdentity> object by calling the static <xref:System.Security.Principal.WindowsIdentity.GetCurrent%2A?displayProperty=nameWithType> method, which queries the current Windows account and places information about that account into the newly created identity object.</span></span> <span data-ttu-id="d6aee-118">다음 코드에서는 새 <xref:System.Security.Principal.WindowsIdentity> 개체를 만들고 현재 인증된 사용자로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="d6aee-118">The following code creates a new <xref:System.Security.Principal.WindowsIdentity> object and initializes it to the current authenticated user.</span></span>  
  
    ```csharp  
    WindowsIdentity myIdentity = WindowsIdentity.GetCurrent();  
    ```  
  
    ```vb  
    Dim myIdentity As WindowsIdentity = WindowsIdentity.GetCurrent()  
    ```  
  
2. <span data-ttu-id="d6aee-119">새 <xref:System.Security.Principal.WindowsPrincipal> 개체를 만들고 이전 단계에서 만든 <xref:System.Security.Principal.WindowsIdentity> 개체의 값을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="d6aee-119">Create a new <xref:System.Security.Principal.WindowsPrincipal> object and pass it the value of the <xref:System.Security.Principal.WindowsIdentity> object created in the preceding step.</span></span>  
  
    ```csharp  
    WindowsPrincipal myPrincipal = new WindowsPrincipal(myIdentity);  
    ```  
  
    ```vb  
    Dim myPrincipal As New WindowsPrincipal(myIdentity)  
    ```  
  
3. <span data-ttu-id="d6aee-120">보안 주체 개체가 생성되면 여러 메서드 중 하나를 사용하여 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6aee-120">When the principal object has been created, you can use one of several methods to validate it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6aee-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6aee-121">See also</span></span>

- [<span data-ttu-id="d6aee-122">Principal 개체 및 Identity 개체</span><span class="sxs-lookup"><span data-stu-id="d6aee-122">Principal and Identity Objects</span></span>](principal-and-identity-objects.md)
- [<span data-ttu-id="d6aee-123">ASP.NET Core 보안</span><span class="sxs-lookup"><span data-stu-id="d6aee-123">ASP.NET Core Security</span></span>](https://docs.microsoft.com/aspnet/core/security/)
