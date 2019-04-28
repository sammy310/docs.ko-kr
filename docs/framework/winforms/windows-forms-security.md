---
title: Windows Forms 보안
ms.date: 03/30/2017
helpviewer_keywords:
- designer access security [Windows Forms]
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms]
- access control [Windows Forms], Windows Forms
- security policy [Windows Forms], Windows Forms
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
ms.openlocfilehash: f64d5ef2e9bb0e977b4c007e8c5109ac0c331a84
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61799374"
---
# <a name="windows-forms-security"></a><span data-ttu-id="2e09a-102">Windows Forms 보안</span><span class="sxs-lookup"><span data-stu-id="2e09a-102">Windows Forms Security</span></span>
<span data-ttu-id="2e09a-103">Windows Forms 코드 기반 (보안 수준이 설정 되는 코드를 실행 하는 사용자에 관계 없이 코드에 대 한) 보안 모델을 갖추고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e09a-103">Windows Forms features a security model that is code-based (security levels are set for code, regardless of the user running the code).</span></span> <span data-ttu-id="2e09a-104">컴퓨터 시스템에 이미 있는 위치에 있을 수 있는 모든 보안 스키마 외에도입니다.</span><span class="sxs-lookup"><span data-stu-id="2e09a-104">This is in addition to any security schemas that may be in place already on your computer system.</span></span> <span data-ttu-id="2e09a-105">(예: 영역을 기반으로 보안 Internet Explorer에서 사용할 수 있는) 브라우저 또는 운영 체제 (예: Windows NT의 자격 증명 기반 보안)에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e09a-105">These can include those in the browser (such as the zone-based security available in Internet Explorer) or the operating system (such as the credential-based security of Windows NT).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2e09a-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="2e09a-106">In This Section</span></span>  
 [<span data-ttu-id="2e09a-107">Windows Forms의 보안 개요</span><span class="sxs-lookup"><span data-stu-id="2e09a-107">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)  
 <span data-ttu-id="2e09a-108">.NET Framework 보안 모델 및 Windows Forms 응용 프로그램에서 확인 하는 데 필요한 기본 단계는 보안에 대해서 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e09a-108">Briefly explains the .NET Framework security model and the basic steps necessary to ensure the Windows Forms in your application are secure.</span></span>  
  
 [<span data-ttu-id="2e09a-109">Windows Forms의 파일 및 데이터 액세스 추가 보안</span><span class="sxs-lookup"><span data-stu-id="2e09a-109">More Secure File and Data Access in Windows Forms</span></span>](more-secure-file-and-data-access-in-windows-forms.md)  
 <span data-ttu-id="2e09a-110">파일 및 부분 신뢰 환경에서 데이터에에서 액세스 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e09a-110">Describes how to access files and data in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="2e09a-111">Windows Forms의 인쇄 추가 보안</span><span class="sxs-lookup"><span data-stu-id="2e09a-111">More Secure Printing in Windows Forms</span></span>](more-secure-printing-in-windows-forms.md)  
 <span data-ttu-id="2e09a-112">부분 신뢰 환경에서 인쇄 기능에 액세스 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e09a-112">Describes how to access printing features in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="2e09a-113">Windows Forms의 추가 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="2e09a-113">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)  
 <span data-ttu-id="2e09a-114">창 조작을 수행, 클립보드 사용 및 부분 신뢰 환경에서 비관리 코드 호출에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e09a-114">Describes performing window manipulation, using the Clipboard, and making calls to unmanaged code in a semi-trusted environment.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2e09a-115">관련 단원</span><span class="sxs-lookup"><span data-stu-id="2e09a-115">Related Sections</span></span>  
 <span data-ttu-id="2e09a-116">[기본 보안 정책](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2e09a-116">[Default Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100))</span></span>  
 <span data-ttu-id="2e09a-117">완전 신뢰, 로컬 인트라넷 및 인터넷 권한 집합에 부여 된 기본 사용 권한을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e09a-117">Lists the default permissions granted in the Full Trust, Local Intranet, and Internet permission sets.</span></span>  
  
 <span data-ttu-id="2e09a-118">[일반 보안 정책 관리](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2e09a-118">[General Security Policy Administration](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))</span></span>  
 <span data-ttu-id="2e09a-119">관리.NET Framework 보안 정책 및 권한 상승에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e09a-119">Gives information about the administering the .NET Framework security policy and elevating permissions.</span></span>  
  
 [<span data-ttu-id="2e09a-120">위험한 권한 및 정책 관리</span><span class="sxs-lookup"><span data-stu-id="2e09a-120">Dangerous Permissions and Policy Administration</span></span>](../misc/dangerous-permissions-and-policy-administration.md)  
 <span data-ttu-id="2e09a-121">일부 잠재적으로 보안 시스템을 손상 시킬 수 있는.net Framework 사용 권한에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e09a-121">Discusses some of the.NET Framework permissions that can potentially allow the security system to be circumvented.</span></span>  
  
 [<span data-ttu-id="2e09a-122">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="2e09a-122">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="2e09a-123">안전 하 게.NET Framework에 대 한 코드를 작성 하기 위한 모범 사례를 설명 하는 항목에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e09a-123">Links to topics that explain the best practices for securely writing code against the .NET Framework.</span></span>  
  
 <span data-ttu-id="2e09a-124">[권한 요청](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2e09a-124">[Requesting Permissions](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100))</span></span>  
 <span data-ttu-id="2e09a-125">코드를 실행 해야 합니다. 사용 권한은 런타임에 알려 주는 특성의 사용을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e09a-125">Discusses the use of attributes to let the runtime know what permissions your code needs to run.</span></span>  
  
 [<span data-ttu-id="2e09a-126">주요 보안 개념</span><span class="sxs-lookup"><span data-stu-id="2e09a-126">Key Security Concepts</span></span>](../../standard/security/key-security-concepts.md)  
 <span data-ttu-id="2e09a-127">코드 보안의 기본 사항을 설명 하는 항목에 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e09a-127">Links to topics that cover the basic aspects of code security.</span></span>  
  
 [<span data-ttu-id="2e09a-128">코드 액세스 보안 기본 사항</span><span class="sxs-lookup"><span data-stu-id="2e09a-128">Code Access Security Basics</span></span>](../misc/code-access-security-basics.md)  
 <span data-ttu-id="2e09a-129">보안 정책을 실행 하는.NET Framework를 사용 하는 기본 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e09a-129">Discusses the basics of working with the .NET Framework run time security policy.</span></span>  
  
 <span data-ttu-id="2e09a-130">[보안 정책을 수정 하려면 시기 결정](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xky659fc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2e09a-130">[Determining When to Modify Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xky659fc(v=vs.100))</span></span>  
 <span data-ttu-id="2e09a-131">응용 프로그램에서 기본 보안 정책에서 분기 해야 하는 시기를 결정 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e09a-131">Explains how to determine when your applications need to diverge from the default security policy.</span></span>  
  
 <span data-ttu-id="2e09a-132">[보안 정책 배포](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/13wcxx6y(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2e09a-132">[Deploying Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/13wcxx6y(v=vs.100))</span></span>  
 <span data-ttu-id="2e09a-133">보안 정책 변경 내용을 배포 하는 최상의 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e09a-133">Discusses the best manner for deploying security policy changes.</span></span>
