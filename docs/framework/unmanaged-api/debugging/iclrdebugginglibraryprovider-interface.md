---
title: ICLRDebuggingLibraryProvider 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider
helpviewer_keywords:
- ICLRDebuggingLibraryProvider interface [.NET Framework debugging]
ms.assetid: 67739617-6add-41a9-9de5-a3200c3109ce
topic_type:
- apiref
ms.openlocfilehash: 77c2011ce677d1bd2823d47740782f48151b408a
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860288"
---
# <a name="iclrdebugginglibraryprovider-interface"></a>ICLRDebuggingLibraryProvider 인터페이스
요청 시 공용 언어 런타임 버전별 디버깅 라이브러리를 찾고 로드 하는 데 사용할 수 있는 라이브러리 공급자 콜백 인터페이스를 가져오는 [ProvideLibrary method](iclrdebugginglibraryprovider-providelibrary-method.md) 메서드를 포함 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|Description|  
|------------|-----------------|  
|[ProvideLibrary 메서드](iclrdebugginglibraryprovider-providelibrary-method.md)|디버거가 디버그 라이브러리를 로드 하는 데 사용할 수 있는 모듈에 대 한 핸들을 제공할 수 있도록 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
