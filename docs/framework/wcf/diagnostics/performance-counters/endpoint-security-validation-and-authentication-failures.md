---
title: '엔드포인트: Security Validation and Authentication Failures'
ms.date: 03/30/2017
ms.assetid: 5bad60aa-6084-4c7b-aefd-9b581f04382e
ms.openlocfilehash: a9a4758b26c744c55af200aee22a7e90c5a5cf57
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256471"
---
# <a name="endpoint-security-validation-and-authentication-failures"></a>엔드포인트: Security Validation and Authentication Failures

카운터 이름: Security Validation and Authentication Failures  
  
## <a name="description"></a>Description  

 이 카운터는 "Security Calls Not Authorized" 카운터로 처리되지 않는 보안 문제 때문에 메시지가 거부될 때마다 증가합니다. 이러한 문제는 다음과 같습니다.  
  
- 클라이언트 토큰을 메시지에서 읽을 수 없습니다.  
  
- 클라이언트 토큰에서 인증에 실패했습니다(잘못된 암호).  
  
- 서명 확인에 실패했습니다(메시지 변조).  
  
- 메시지가 이전 메시지와 중복됩니다. 이러한 현상은 재생 공격 중에 나타날 수 있습니다.  
  
- 해독 오류가 발생했습니다.  
  
- 일부 필수 요소(타임스탬프 또는 암호화된 데이터 블록)가 메시지에 없습니다.  
  
- TLSNEGO/SPNEGO 핸드셰이크 중에 오류가 발생했습니다.
