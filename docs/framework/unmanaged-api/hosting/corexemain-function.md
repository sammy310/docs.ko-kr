---
title: _CorExeMain 함수
ms.date: 03/30/2017
api_name:
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7407db297a827004c851b904b2da8652778cb08
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177491"
---
# <a name="corexemain-function"></a>_CorExeMain 함수
CLR (공용 언어 런타임)을 초기화 하 고 실행 가능한 어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾습니다 실행을 시작 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a>설명  
 이 함수는 관리 되는 실행 가능한 어셈블리에서 생성 된 프로세스에서 로더에 의해 호출 됩니다. 로더가 DLL 어셈블리에 대 한 호출을 [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) 함수를 대신 합니다.  
  
 운영 체제 로더는 이미지 파일에 지정 된 진입점에 관계 없이이 메서드를 호출 합니다.  
  
 Windows 98, Windows ME, Windows NT 및 Windows 2000에는 `_CorExeMain` 함수 픽스업에 운영 체제 로더를 통해 간접적으로 호출 됩니다. 다른 모든 버전의 Windows에서는 운영 체제 로더에 의해 직접 호출 됩니다.  
  
 자세한 내용은 주의 섹션을 참조 합니다 [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) 항목입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [메타데이터 전역 정적 함수](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
