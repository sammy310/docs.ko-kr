---
description: '자세히 알아보기: ICLRStrongName2 인터페이스'
title: ICLRStrongName2 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRStrongName2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName2
helpviewer_keywords:
- ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type:
- apiref
ms.openlocfilehash: 7442bd054af735e9f1b75b05feb8724dfa993f73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781794"
---
# <a name="iclrstrongname2-interface"></a>ICLRStrongName2 인터페이스

에서는 sha-1 512 384 256 (Secure Hash algorithm)의 SHA-2 그룹을 사용 하 여 강력한 이름을 만들 수 있는 기능을 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[StrongNameGetPublicKeyEx 메서드](strongnamegetpublickeyex-method.md)|공개/개인 키 쌍에서 공개 키를 가져오고 해시 알고리즘과 서명 알고리즘을 지정 합니다.|  
|[StrongNameSignatureVerificationEx2 메서드](strongnamesignatureverificationex2-method.md)|강력한 이름의 어셈블리에 대 한 서명을 확인 하 고 ECMA 키에서 실제 키로의 매핑을 제공 합니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** MetaHost  
  
 **라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
