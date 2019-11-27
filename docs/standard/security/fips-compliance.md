---
title: FIPS 준수-.NET Core
description: .NET Core FIPS(Federal Information Processing Standard) (FIPS) 규정 준수에 대해 설명 합니다.
ms.date: 11/20/2019
author: Rick-Anderson
ms.author: riande
ms.openlocfilehash: cf640c857e79ae811dd38d57a0e5301b7bc96572
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74205079"
---
# <a name="net-core-federal-information-processing-standard-fips-compliance"></a><span data-ttu-id="db2e1-103">.NET Core FIPS(Federal Information Processing Standard) (FIPS) 준수</span><span class="sxs-lookup"><span data-stu-id="db2e1-103">.NET Core Federal Information Processing Standard (FIPS) compliance</span></span>

<span data-ttu-id="db2e1-104">FIPS (FIPS(Federal Information Processing Standard)) 게시 140-2는 정보 기술 제품의 암호화 모듈에 대 한 최소 보안 요구 사항을 정의 하는 미국 정부 표준으로, 정보의 섹션 5131에 정의 되어 있습니다. 1996의 기술 관리 개정 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="db2e1-104">The Federal Information Processing Standard (FIPS) Publication 140-2 is a U.S. government standard that defines minimum security requirements for cryptographic modules in information technology products, as defined in Section 5131 of the Information Technology Management Reform Act of 1996.</span></span>

<span data-ttu-id="db2e1-105">.NET Core:</span><span class="sxs-lookup"><span data-stu-id="db2e1-105">.NET Core:</span></span>

* <span data-ttu-id="db2e1-106">기본 운영 체제에서 제공 하는 표준 모듈을 통해 암호화 기본 호출을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="db2e1-106">Passes cryptographic primitives calls through to the standard modules the underlying operating system provides.</span></span>
* <span data-ttu-id="db2e1-107">는 .NET Core 앱에서 FIPS 승인 알고리즘이 나 키 크기의 사용을 강제 적용 **하지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db2e1-107">Does **not** enforce the use of FIPS Approved algorithms or key sizes in .NET Core apps.</span></span>

<span data-ttu-id="db2e1-108">시스템 관리자는 운영 체제에 대해 FIPS 준수를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db2e1-108">The system administrator is responsible for configuring the FIPS compliance for an operating system.</span></span>

<span data-ttu-id="db2e1-109">FIPS 규격 환경에 대해 코드를 작성 하는 경우 개발자는 비준수 FIPS 알고리즘이 사용 되지 않는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db2e1-109">If code is written for a FIPS-compliant environment, the developer is responsible for ensuring that non-compliant FIPS algorithms aren't used.</span></span>

<span data-ttu-id="db2e1-110">FIPS 규정 준수에 대 한 자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="db2e1-110">For more information on FIPS compliance, see the following articles:</span></span>

* [<span data-ttu-id="db2e1-111">Windows FIPS 준수</span><span class="sxs-lookup"><span data-stu-id="db2e1-111">Windows FIPS Compliance</span></span>](/windows/security/threat-protection/fips-140-validation)
* [<span data-ttu-id="db2e1-112">FIPS 준수를 위한 Windows 구성</span><span class="sxs-lookup"><span data-stu-id="db2e1-112">Configuring Windows for FIPS Compliance</span></span>](/windows/security/threat-protection/security-policy-settings/system-cryptography-use-fips-compliant-algorithms-for-encryption-hashing-and-signing)
* [<span data-ttu-id="db2e1-113">10.2. FIPS (연방 정보 처리 표준)</span><span class="sxs-lookup"><span data-stu-id="db2e1-113">10.2. FEDERAL INFORMATION PROCESSING STANDARD (FIPS)</span></span>](https://access.redhat.com/documentation/red_hat_enterprise_linux/6/html/security_guide/sect-security_guide-federal_standards_and_regulations-federal_information_processing_standard)
