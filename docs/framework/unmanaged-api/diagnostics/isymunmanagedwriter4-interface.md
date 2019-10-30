---
title: ISymUnmanagedWriter4 인터페이스
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: a656777461c50b5a1593917278eb54abda982dc2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134563"
---
# <a name="isymunmanagedwriter4-interface"></a>ISymUnmanagedWriter4 인터페이스
ISymUnmanagedWriter4 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a>메서드  
 이 인터페이스에는 다음과 같은 메서드가 있습니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetDebugInfoWithPadding 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|는 [GetDebugInfo 메서드와](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) 동일 하 게 작동 합니다. 단, 경로 문자열은 종료 null 문자 다음에 0으로 패딩 하 여 문자열 데이터의 고정 크기를 `MAX_PATH`합니다. 패딩은 경로 문자열 길이 자체가 `MAX_PATH`보다 작은 경우에만 지정 됩니다.<br /><br /> 따라서 PE 파일의 차이점을 쉽게 작성할 수 있습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참조

- [진단 기호 저장소 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter3 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
