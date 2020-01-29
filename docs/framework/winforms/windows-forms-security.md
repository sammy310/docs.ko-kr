---
title: 보안
ms.date: 03/30/2017
helpviewer_keywords:
- designer access security [Windows Forms]
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms]
- access control [Windows Forms], Windows Forms
- security policy [Windows Forms], Windows Forms
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
ms.openlocfilehash: a3debf487b9b2a04277d9ce3007f28662fa4899e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734495"
---
# <a name="windows-forms-security"></a><span data-ttu-id="51a41-102">Windows Forms 보안</span><span class="sxs-lookup"><span data-stu-id="51a41-102">Windows Forms Security</span></span>
<span data-ttu-id="51a41-103">Windows Forms은 코드를 기반으로 하는 보안 모델을 제공 합니다. 코드를 실행 하는 사용자에 관계 없이 코드에 대해 보안 수준이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51a41-103">Windows Forms features a security model that is code-based (security levels are set for code, regardless of the user running the code).</span></span> <span data-ttu-id="51a41-104">이는 컴퓨터 시스템에 이미 포함 되어 있을 수 있는 모든 보안 스키마에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51a41-104">This is in addition to any security schemas that may be in place already on your computer system.</span></span> <span data-ttu-id="51a41-105">여기에는 브라우저에 있는 영역 기반 보안 (예: Internet Explorer에서 사용 가능한 영역 기반 보안) 또는 운영 체제 (예: Windows NT의 자격 증명 기반 보안)가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51a41-105">These can include those in the browser (such as the zone-based security available in Internet Explorer) or the operating system (such as the credential-based security of Windows NT).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="51a41-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="51a41-106">In This Section</span></span>  
 [<span data-ttu-id="51a41-107">Windows Forms의 보안 개요</span><span class="sxs-lookup"><span data-stu-id="51a41-107">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)  
 <span data-ttu-id="51a41-108">응용 프로그램의 Windows Forms를 안전 하 게 보호 하는 데 필요한 .NET Framework 보안 모델 및 기본 단계에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="51a41-108">Briefly explains the .NET Framework security model and the basic steps necessary to ensure the Windows Forms in your application are secure.</span></span>  
  
 [<span data-ttu-id="51a41-109">Windows Forms의 파일 및 데이터 액세스 추가 보안</span><span class="sxs-lookup"><span data-stu-id="51a41-109">More Secure File and Data Access in Windows Forms</span></span>](more-secure-file-and-data-access-in-windows-forms.md)  
 <span data-ttu-id="51a41-110">부분적으로 신뢰할 수 있는 환경에서 파일 및 데이터에 액세스 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="51a41-110">Describes how to access files and data in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="51a41-111">Windows Forms의 인쇄 추가 보안</span><span class="sxs-lookup"><span data-stu-id="51a41-111">More Secure Printing in Windows Forms</span></span>](more-secure-printing-in-windows-forms.md)  
 <span data-ttu-id="51a41-112">부분적으로 신뢰할 수 있는 환경에서 인쇄 기능에 액세스 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="51a41-112">Describes how to access printing features in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="51a41-113">Windows Forms의 추가 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="51a41-113">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)  
 <span data-ttu-id="51a41-114">창 조작 수행, 클립보드 사용 및 부분 신뢰 환경에서 비관리 코드 호출을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="51a41-114">Describes performing window manipulation, using the Clipboard, and making calls to unmanaged code in a semi-trusted environment.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="51a41-115">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="51a41-115">Related Sections</span></span>  
 <span data-ttu-id="51a41-116">[기본 보안 정책](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="51a41-116">[Default Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100))</span></span>  
 <span data-ttu-id="51a41-117">완전 신뢰, 로컬 인트라넷 및 인터넷 권한 집합에 부여 된 기본 사용 권한을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="51a41-117">Lists the default permissions granted in the Full Trust, Local Intranet, and Internet permission sets.</span></span>  
  
 <span data-ttu-id="51a41-118">[일반 보안 정책 관리](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="51a41-118">[General Security Policy Administration](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))</span></span>  
 <span data-ttu-id="51a41-119">.NET Framework 보안 정책 관리 및 권한 상승에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="51a41-119">Gives information about the administering the .NET Framework security policy and elevating permissions.</span></span>  
  
 [<span data-ttu-id="51a41-120">위험한 권한 및 정책 관리</span><span class="sxs-lookup"><span data-stu-id="51a41-120">Dangerous Permissions and Policy Administration</span></span>](../misc/dangerous-permissions-and-policy-administration.md)  
 <span data-ttu-id="51a41-121">잠재적으로 보안 시스템을 우회할 수 있는 the.NET Framework 사용 권한에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="51a41-121">Discusses some of the.NET Framework permissions that can potentially allow the security system to be circumvented.</span></span>  
  
 [<span data-ttu-id="51a41-122">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="51a41-122">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="51a41-123">.NET Framework에 대 한 코드를 안전 하 게 작성 하기 위한 모범 사례를 설명 하는 항목으로 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="51a41-123">Links to topics that explain the best practices for securely writing code against the .NET Framework.</span></span>  
  
 <span data-ttu-id="51a41-124">[권한 요청](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="51a41-124">[Requesting Permissions](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100))</span></span>  
 <span data-ttu-id="51a41-125">런타임에 코드에서 실행 해야 하는 권한을 알 수 있도록 특성 사용에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="51a41-125">Discusses the use of attributes to let the runtime know what permissions your code needs to run.</span></span>  
  
 [<span data-ttu-id="51a41-126">주요 보안 개념</span><span class="sxs-lookup"><span data-stu-id="51a41-126">Key Security Concepts</span></span>](../../standard/security/key-security-concepts.md)  
 <span data-ttu-id="51a41-127">코드 보안의 기본 측면을 다루는 항목에 대 한 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="51a41-127">Links to topics that cover the basic aspects of code security.</span></span>  
  
 [<span data-ttu-id="51a41-128">코드 액세스 보안 기본 사항</span><span class="sxs-lookup"><span data-stu-id="51a41-128">Code Access Security Basics</span></span>](../misc/code-access-security-basics.md)  
 <span data-ttu-id="51a41-129">.NET Framework 실행 시간 보안 정책을 사용 하는 기본 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="51a41-129">Discusses the basics of working with the .NET Framework run time security policy.</span></span>  
  
 <span data-ttu-id="51a41-130">[보안 정책을 수정할 시기 결정](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xky659fc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="51a41-130">[Determining When to Modify Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xky659fc(v=vs.100))</span></span>  
 <span data-ttu-id="51a41-131">응용 프로그램이 기본 보안 정책에서 분기 되어야 하는 시기를 결정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="51a41-131">Explains how to determine when your applications need to diverge from the default security policy.</span></span>  
  
 <span data-ttu-id="51a41-132">[보안 정책 배포](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/13wcxx6y(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="51a41-132">[Deploying Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/13wcxx6y(v=vs.100))</span></span>  
 <span data-ttu-id="51a41-133">보안 정책 변경 내용을 배포 하는 가장 좋은 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="51a41-133">Discusses the best manner for deploying security policy changes.</span></span>
