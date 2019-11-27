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
# <a name="net-core-federal-information-processing-standard-fips-compliance"></a>.NET Core FIPS(Federal Information Processing Standard) (FIPS) 준수

FIPS (FIPS(Federal Information Processing Standard)) 게시 140-2는 정보 기술 제품의 암호화 모듈에 대 한 최소 보안 요구 사항을 정의 하는 미국 정부 표준으로, 정보의 섹션 5131에 정의 되어 있습니다. 1996의 기술 관리 개정 동작입니다.

.NET Core:

* 기본 운영 체제에서 제공 하는 표준 모듈을 통해 암호화 기본 호출을 전달 합니다.
* 는 .NET Core 앱에서 FIPS 승인 알고리즘이 나 키 크기의 사용을 강제 적용 **하지** 않습니다.

시스템 관리자는 운영 체제에 대해 FIPS 준수를 구성 해야 합니다.

FIPS 규격 환경에 대해 코드를 작성 하는 경우 개발자는 비준수 FIPS 알고리즘이 사용 되지 않는지 확인 해야 합니다.

FIPS 규정 준수에 대 한 자세한 내용은 다음 문서를 참조 하세요.

* [Windows FIPS 준수](/windows/security/threat-protection/fips-140-validation)
* [FIPS 준수를 위한 Windows 구성](/windows/security/threat-protection/security-policy-settings/system-cryptography-use-fips-compliant-algorithms-for-encryption-hashing-and-signing)
* [10.2. FIPS (연방 정보 처리 표준)](https://access.redhat.com/documentation/red_hat_enterprise_linux/6/html/security_guide/sect-security_guide-federal_standards_and_regulations-federal_information_processing_standard)
