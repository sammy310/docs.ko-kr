---
ms.openlocfilehash: c5a061dffa1deb66e1769d6ec70dfa2155ac6a31
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615710"
---
### <a name="calling-createdefaultauthorizationcontext-with-a-null-argument-has-changed"></a><span data-ttu-id="61c12-101">Null 인수를 사용한 CreateDefaultAuthorizationContext 호출이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="61c12-101">Calling CreateDefaultAuthorizationContext with a null argument has changed</span></span>

#### <a name="details"></a><span data-ttu-id="61c12-102">설명</span><span class="sxs-lookup"><span data-stu-id="61c12-102">Details</span></span>

<span data-ttu-id="61c12-103">Null authorizationPolicies를 사용하는 <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=fullName>에 대한 호출로 반환된 <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=fullName>의 구현이 .NET Framework 4.6에서 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="61c12-103">The implementation of the <xref:System.IdentityModel.Policy.AuthorizationContext?displayProperty=fullName> returned by a call to the <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=fullName> with a null authorizationPolicies argument has changed its implementation in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="61c12-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="61c12-104">Suggestion</span></span>

<span data-ttu-id="61c12-105">드문 경우이지만 사용자 지정 인증을 사용하는 WCF 앱은 다르게 동작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c12-105">In rare cases, WCF apps that use custom authentication may see behavioral differences.</span></span> <span data-ttu-id="61c12-106">이러한 경우 두 가지 방법 중 하나로 이전 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c12-106">In such cases, the previous behavior can be restored in either of two ways:</span></span>

- <span data-ttu-id="61c12-107">4\.6 이전 버전의 .NET Framework를 대상으로 사용하도록 앱을 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="61c12-107">Recompile your app to target an earlier version of the .NET Framework than 4.6.</span></span> <span data-ttu-id="61c12-108">IIS 호스트 서비스의 경우 이전 버전의.NET Framework를 대상으로 하는 `<httpRuntime targetFramework="x.x">` 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61c12-108">For IIS-hosted services, use the `<httpRuntime targetFramework="x.x">` element to target an earlier version of the .NET Framework.</span></span>
- <span data-ttu-id="61c12-109">다음 줄을 app.config 파일의 `<appSettings>` 섹션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="61c12-109">Add the following line to the `<appSettings>` section of your app.config file:</span></span>

    ```xml
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />
    ```

| <span data-ttu-id="61c12-110">이름</span><span class="sxs-lookup"><span data-stu-id="61c12-110">Name</span></span>    | <span data-ttu-id="61c12-111">값</span><span class="sxs-lookup"><span data-stu-id="61c12-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="61c12-112">Scope</span><span class="sxs-lookup"><span data-stu-id="61c12-112">Scope</span></span>   | <span data-ttu-id="61c12-113">부</span><span class="sxs-lookup"><span data-stu-id="61c12-113">Minor</span></span>       |
| <span data-ttu-id="61c12-114">버전</span><span class="sxs-lookup"><span data-stu-id="61c12-114">Version</span></span> | <span data-ttu-id="61c12-115">4.6</span><span class="sxs-lookup"><span data-stu-id="61c12-115">4.6</span></span>         |
| <span data-ttu-id="61c12-116">형식</span><span class="sxs-lookup"><span data-stu-id="61c12-116">Type</span></span>    | <span data-ttu-id="61c12-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="61c12-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="61c12-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="61c12-118">Affected APIs</span></span>

- <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext(System.Collections.Generic.IList{System.IdentityModel.Policy.IAuthorizationPolicy})?displayProperty=nameWithType>
