---
title: CoEEShutDownCOM 함수
ms.date: 03/30/2017
api_name:
- CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoEEShutDownCOM
helpviewer_keywords:
- CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ddef35b1b707cc5c962402e880923dca7d4d9d6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208152"
---
# <a name="coeeshutdowncom-function"></a>CoEEShutDownCOM 함수
CLR (공용 언어 런타임) 런타임 호출 가능 래퍼 (RCW) 내에서 보유 하는 모든 인터페이스 포인터가 해제 되도록 합니다. 이 효과가 모든 RCW 캐시를 해제 합니다. 이 전역 함수에서 사용 되지 않습니다는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다. 대신, 특정 런타임에 대 한 진입점을 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a>설명  
 `CoEEShutDownCOM` 함수는 먼저 모든 컨텍스트 및 모든 캐시에 있는 모든 Rcw를 해제 하 고 다음 설치 프로그램에서 기존의 모든 중지 알림을 제거 합니다. DLL 언로드 없습니다 발생합니다.  
  
> [!CAUTION]
>  이 함수는 모든 런타임을 프로세스로 로드 되는 영향을 줍니다.  
  
 부터는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], 영향을 주려는 특정 런타임에서이 함수에 대 한 진입점을 호출 합니다. 진입점을 가져오려면 호출 합니다 [iclrruntimeinfo:: Getprocaddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) 메서드 "CoEEShutDownCOM"를 지정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [메타데이터 전역 정적 함수](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
