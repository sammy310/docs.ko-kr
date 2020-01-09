---
title: 보안 ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
ms.openlocfilehash: c443bda8cdc2c6b32760e9dcba8b81a29d81660b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715933"
---
# <a name="security-etw-events"></a>보안 ETW 이벤트

보안 이벤트는 강력한 이름 확인 및 Authenticode 확인 중에 발생합니다.  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a>StrongNameVerificationStart_V1 및 StrongNameVerificationStop_V1 이벤트  
 다음 표에서는 키워드와 수준을 보여 줍니다. 자세한 내용은 [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md)을 참조하세요.  
  
|이벤트를 발생시키기 위한 키워드|수준|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0x400)|정보 제공(4)|  
  
 다음 표에서는 이벤트 정보를 보여 줍니다.  
  
|Event|이벤트 ID|발생 시기|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|181|강력한 이름 확인의 시작입니다.|  
|`StrongNameVerificationStop_V1`|182|강력한 이름 확인의 끝입니다.|  
  
 다음 표에서는 이벤트 데이터를 보여 줍니다.  
  
|필드 이름|데이터 형식|설명|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|확인 플래그입니다.|  
|ErrorCode|win:UInt32|HResult 오류 코드입니다.|  
|FullyQualifiedAssemblyName|win:UnicodeString|정규화된 어셈블리 이름입니다.|  
|ClrInstanceID|win:UInt16|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a>AuthenticodeVerificationStart_V1 및 AuthenticodeVerificationStop_V1 이벤트  
 다음 표에서는 키워드와 수준을 보여 줍니다.  
  
|이벤트를 발생시키기 위한 키워드|수준|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0x400)|정보 제공(4)|  
  
 다음 표에서는 이벤트 정보를 보여 줍니다.  
  
|Event|이벤트 ID|발생 시기|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|183|Authenticode 확인의 시작입니다.|  
|`AuthenticodeVerificationStop_V1`|184|Authenticode 확인의 끝입니다.|  
  
 다음 표에서는 이벤트 데이터를 보여 줍니다.  
  
|필드 이름|데이터 형식|설명|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|확인 플래그입니다.|  
|ErrorCode|win:UInt32|HResult 오류 코드입니다.|  
|ModulePath|win:UnicodeString|모듈 경로입니다.|  
|ClrInstanceID|win:UInt16|CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.|  
  
## <a name="see-also"></a>참조

- [CLR ETW 이벤트](clr-etw-events.md)
