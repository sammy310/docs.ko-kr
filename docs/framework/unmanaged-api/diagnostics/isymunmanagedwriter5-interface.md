---
title: ISymUnmanagedWriter5 인터페이스
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
ms.openlocfilehash: d9204457b71b670e1c96ed228ad11116bdf41fe6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493580"
---
# <a name="isymunmanagedwriter5-interface"></a>ISymUnmanagedWriter5 인터페이스
ISymUnmanagedWriter5 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a>메서드  
 이 인터페이스에는 다음과 같은 메서드가 있습니다.  
  
|방법|설명|  
|------------|-----------------|  
|[CloseMapTokensToSourceSpans 메서드](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|토큰-소스 범위 매핑 정보에 대 한 특수 사용자 지정 데이터 섹션을 닫습니다. 닫힌 후에는 더 이상 매핑 정보를 추가할 수 없습니다.|  
|[MapTokenToSourceSpan 메서드](isymunmanagedwriter5-maptokentosourcespan-method.md)|지정 된 소스 파일의 지정 된 소스 줄 범위에 지정 된 메타 데이터 토큰을 매핑합니다.<br /><br /> [OpenMapTokensToSourceSpans method](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) 및 [CloseMapTokensToSourceSpans 메서드에](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)대 한 호출 사이에 호출 해야 합니다.|  
|[OpenMapTokensToSourceSpans 메서드](isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|특수 한 사용자 지정 데이터 섹션을 열어 토큰 대 소스 범위 매핑 정보를로 내보냅니다. 메서드가 이미 열려 있거나 그 반대의 경우에는이 섹션을 열 때 오류가 발생 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [진단 기호 저장소 인터페이스](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter4 인터페이스](isymunmanagedwriter4-interface.md)
