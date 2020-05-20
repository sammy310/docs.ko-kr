---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding 메서드
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
ms.openlocfilehash: cfc6c22558cee780823c8cca0c36b883147e9496
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614645"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a>ISymUnmanagedWriter4::GetDebugInfoWithPadding 메서드
는 [GetDebugInfo 메서드와](isymunmanagedwriter-getdebuginfo-method.md) 동일 하 게 작동 합니다. 단, 경로 문자열은 종료 null 문자 다음에 0으로 채워져 문자열 데이터의 고정 크기를 만듭니다 `MAX_PATH` . 패딩은 경로 문자열 길이 자체가 보다 작은 경우에만 지정 됩니다 `MAX_PATH` .  
  
 따라서 PE 파일의 차이점을 쉽게 작성할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a>Return Value  
 `HRESULT`를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [ISymUnmanagedWriter4 인터페이스](isymunmanagedwriter4-interface.md)
