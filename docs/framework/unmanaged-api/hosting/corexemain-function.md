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
ms.openlocfilehash: af1d0e2039024a51341e30bec497c581a0bcacb3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673672"
---
# <a name="_corexemain-function"></a>_CorExeMain 함수

CLR (공용 언어 런타임)을 초기화 하 고, 실행 가능한 어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾고, 실행을 시작 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a>설명  

 이 함수는 관리 되는 실행 어셈블리에서 만든 프로세스의 로더에서 호출 됩니다. DLL 어셈블리의 경우 로더는 대신 [_CorDllMain](cordllmain-function.md) 함수를 호출 합니다.  
  
 운영 체제 로더는 이미지 파일에 지정 된 진입점에 관계 없이이 메서드를 호출 합니다.  
  
 Windows 98, Windows ME, Windows NT 및 Windows 2000에서 `_CorExeMain` 함수는 운영 체제 로더에서 픽스업을 통해 간접적으로 호출 됩니다. 다른 모든 버전의 Windows에서는 운영 체제 로더에서 직접 호출 합니다.  
  
 자세한 내용은 [_CorValidateImage](corvalidateimage-function.md) 항목의 설명 섹션을 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [메타데이터 전역 정적 함수](../metadata/metadata-global-static-functions.md)
