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
ms.openlocfilehash: 0d2b82bc056acd2e620461081b5f8c9d45fc152c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490636"
---
# <a name="coeeshutdowncom-function"></a>CoEEShutDownCOM 함수
CLR (공용 언어 런타임) 런타임 호출 가능 래퍼 (RCW) 내에서 보유 하는 모든 인터페이스 포인터가 해제 되도록 합니다. 이 효과가 모든 RCW 캐시를 해제 합니다. 이 전역 함수는.NET Framework 4에서 사용 되지 않습니다. 대신, 특정 런타임에 대 한 진입점을 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a>설명  
 `CoEEShutDownCOM` 함수는 먼저 모든 컨텍스트 및 모든 캐시에 있는 모든 Rcw를 해제 하 고 다음 설치 프로그램에서 기존의 모든 중지 알림을 제거 합니다. DLL 언로드 없습니다 발생합니다.  
  
> [!CAUTION]
>  이 함수는 모든 런타임을 프로세스로 로드 되는 영향을 줍니다.  
  
 .NET Framework 4 부터는이 영향을 주려는 특정 런타임이 함수에 대 한 진입점을 호출 합니다. 진입점을 가져오려면 호출 합니다 [iclrruntimeinfo:: Getprocaddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) 메서드 "CoEEShutDownCOM"를 지정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [메타데이터 전역 정적 함수](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
