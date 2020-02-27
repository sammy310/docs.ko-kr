---
title: FIPS 준수-.NET Core
description: .NET Core FIPS(Federal Information Processing Standard) (FIPS) 규정 준수에 대해 설명 합니다.
ms.date: 11/20/2019
author: Rick-Anderson
ms.author: riande
ms.openlocfilehash: 84d6edc6975af0484bb67999ad5891eaf4db057d
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626960"
---
# <a name="net-core-federal-information-processing-standard-fips-compliance"></a><span data-ttu-id="a9d9f-103">.NET Core FIPS(Federal Information Processing Standard) (FIPS) 준수</span><span class="sxs-lookup"><span data-stu-id="a9d9f-103">.NET Core Federal Information Processing Standard (FIPS) compliance</span></span>

<span data-ttu-id="a9d9f-104">FIPS (FIPS(Federal Information Processing Standard)) 게시 140-2는 정보 기술 제품의 암호화 모듈에 대 한 최소 보안 요구 사항을 정의 하는 미국 정부 표준으로, 정보의 섹션 5131에 정의 되어 있습니다. 1996의 기술 관리 개정 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="a9d9f-104">The Federal Information Processing Standard (FIPS) Publication 140-2 is a U.S. government standard that defines minimum security requirements for cryptographic modules in information technology products, as defined in Section 5131 of the Information Technology Management Reform Act of 1996.</span></span>

<span data-ttu-id="a9d9f-105">.NET Core:</span><span class="sxs-lookup"><span data-stu-id="a9d9f-105">.NET Core:</span></span>

* <span data-ttu-id="a9d9f-106">기본 운영 체제에서 제공 하는 표준 모듈을 통해 암호화 기본 호출을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d9f-106">Passes cryptographic primitives calls through to the standard modules the underlying operating system provides.</span></span>
* <span data-ttu-id="a9d9f-107">는 .NET Core 앱에서 FIPS 승인 알고리즘이 나 키 크기의 사용을 강제 적용 **하지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d9f-107">Does **not** enforce the use of FIPS Approved algorithms or key sizes in .NET Core apps.</span></span>

<span data-ttu-id="a9d9f-108">시스템 관리자는 운영 체제에 대해 FIPS 준수를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d9f-108">The system administrator is responsible for configuring the FIPS compliance for an operating system.</span></span>

<span data-ttu-id="a9d9f-109">FIPS 규격 환경에 대해 코드를 작성 하는 경우 개발자는 비준수 FIPS 알고리즘이 사용 되지 않는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d9f-109">If code is written for a FIPS-compliant environment, the developer is responsible for ensuring that non-compliant FIPS algorithms aren't used.</span></span>

<span data-ttu-id="a9d9f-110">FIPS 규정 준수에 대 한 자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9d9f-110">For more information on FIPS compliance, see the following articles:</span></span>

* [<span data-ttu-id="a9d9f-111">Windows FIPS 준수</span><span class="sxs-lookup"><span data-stu-id="a9d9f-111">Windows FIPS Compliance</span></span>](/windows/security/threat-protection/fips-140-validation)
* [<span data-ttu-id="a9d9f-112">FIPS 준수를 위한 Windows 구성</span><span class="sxs-lookup"><span data-stu-id="a9d9f-112">Configuring Windows for FIPS Compliance</span></span>](/windows/security/threat-protection/security-policy-settings/system-cryptography-use-fips-compliant-algorithms-for-encryption-hashing-and-signing)
* [<span data-ttu-id="a9d9f-113">8 장. 연방 표준 및 규정 Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="a9d9f-113">Chapter 8. Federal Standards and Regulations Red Hat Enterprise Linux 7</span></span>](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/security_guide/chap-federal_standards_and_regulations)
