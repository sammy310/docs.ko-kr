---
title: 어셈블리 바인딩 리디렉션 보안 권한
description: .NET의 응용 프로그램 구성 파일에서 명시적 어셈블리 바인딩 리디렉션에 필요한 보안 권한에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
ms.openlocfilehash: ea2b735b2c98b588903c4393f21c6b743910854a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552377"
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="f8b0f-103">어셈블리 바인딩 리디렉션 보안 권한</span><span class="sxs-lookup"><span data-stu-id="f8b0f-103">Assembly Binding Redirection Security Permission</span></span>
<span data-ttu-id="f8b0f-104">애플리케이션 구성 파일에서 어셈블리 바인딩을 명시적으로 리디렉션하려면 보안 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f8b0f-104">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="f8b0f-105">이는 .NET Framework 어셈블리와 타사 어셈블리의 리디렉션 모두에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8b0f-105">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="f8b0f-106">에 플래그를 설정 하 여 사용 권한을 부여 합니다 <xref:System.Security.Permissions.SecurityPermissionFlag> <xref:System.Security.Permissions.SecurityPermission> .</span><span class="sxs-lookup"><span data-stu-id="f8b0f-106">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="f8b0f-107">관리 되는 어셈블리에는 기본적으로 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8b0f-107">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="f8b0f-108">보안 권한은 신뢰할 수 있는 영역 (로컬 컴퓨터) 및 인트라넷 영역에서 실행 되는 응용 프로그램에 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8b0f-108">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="f8b0f-109">인터넷 영역에서 실행 되는 응용 프로그램은 어셈블리 바인딩 리디렉션을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8b0f-109">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="f8b0f-110">구성 요소 게시자가 제어 하는 게시자 정책 파일 또는 관리자가 제어 하는 컴퓨터 구성 파일에서 어셈블리 리디렉션을 수행 하는 경우에는이 권한이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8b0f-110">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="f8b0f-111">그러나 응용 프로그램 [\<publisherPolicy apply="no"/>](./file-schema/runtime/publisherpolicy-element.md) 에서 응용 프로그램 구성 파일의 요소를 사용 하 여 게시자 정책을 명시적으로 무시 하려면 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8b0f-111">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](./file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="f8b0f-112">다음 표에서는 **Bindingredirects** 플래그에 대 한 기본 보안 설정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8b0f-112">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="f8b0f-113">영역</span><span class="sxs-lookup"><span data-stu-id="f8b0f-113">Zone</span></span>|<span data-ttu-id="f8b0f-114">BindingRedirects 플래그 설정</span><span class="sxs-lookup"><span data-stu-id="f8b0f-114">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="f8b0f-115">신뢰할 수 있는 영역 (로컬 컴퓨터)</span><span class="sxs-lookup"><span data-stu-id="f8b0f-115">Trusted Zone (local machine)</span></span>|<span data-ttu-id="f8b0f-116">**ON**</span><span class="sxs-lookup"><span data-stu-id="f8b0f-116">**ON**</span></span>|  
|<span data-ttu-id="f8b0f-117">인트라넷 영역</span><span class="sxs-lookup"><span data-stu-id="f8b0f-117">Intranet Zone</span></span>|<span data-ttu-id="f8b0f-118">**ON**</span><span class="sxs-lookup"><span data-stu-id="f8b0f-118">**ON**</span></span>|  
|<span data-ttu-id="f8b0f-119">인터넷 영역</span><span class="sxs-lookup"><span data-stu-id="f8b0f-119">Internet Zone</span></span>|<span data-ttu-id="f8b0f-120">**OFF**</span><span class="sxs-lookup"><span data-stu-id="f8b0f-120">**OFF**</span></span>|  
|<span data-ttu-id="f8b0f-121">신뢰할 수 없는 영역</span><span class="sxs-lookup"><span data-stu-id="f8b0f-121">Untrusted zones</span></span>|<span data-ttu-id="f8b0f-122">**OFF**</span><span class="sxs-lookup"><span data-stu-id="f8b0f-122">**OFF**</span></span>|  
  
 <span data-ttu-id="f8b0f-123">관리자는 이러한 보안 설정을 변경 하 여 지정 된 컴퓨터의 특정 시나리오를 지원 하거나 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8b0f-123">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="f8b0f-124">**바인딩 리디렉션** 플래그 설정을 기본값에서 변경 하는 데 사용할 수 있는 도구가 없습니다. 관리자는 사용자 컴퓨터에서 Security.config 파일을 수동으로 편집 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8b0f-124">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8b0f-125">참조</span><span class="sxs-lookup"><span data-stu-id="f8b0f-125">See also</span></span>

- <span data-ttu-id="f8b0f-126">[게시자 정책 파일 및 Side-by-Side 실행](/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f8b0f-126">[Publisher Policy Files and Side-by-Side Execution](/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))</span></span>
- [<span data-ttu-id="f8b0f-127">방법: 자동 바인딩 리디렉션 사용 설정 및 해제</span><span class="sxs-lookup"><span data-stu-id="f8b0f-127">How to: Enable and Disable Automatic Binding Redirection</span></span>](how-to-enable-and-disable-automatic-binding-redirection.md)
- [<span data-ttu-id="f8b0f-128">Side-by-Side 실행</span><span class="sxs-lookup"><span data-stu-id="f8b0f-128">Side-by-Side Execution</span></span>](../deployment/side-by-side-execution.md)
