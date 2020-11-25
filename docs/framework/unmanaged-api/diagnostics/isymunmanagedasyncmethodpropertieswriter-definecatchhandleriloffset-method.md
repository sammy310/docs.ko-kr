---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 메서드
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
ms.openlocfilehash: a37d319a39b959700944f9e111d2945e286c99ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707141"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a>ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 메서드

비동기 메서드를 래핑하는 컴파일러 생성 catch 처리기에 대 한 IL 오프셋을 설정 합니다.  
  
 생성 된 catch의 IL 오프셋은 디버거에서 사용자 코드 메서드에서 발생할 수 있는 경우에도 사용자가 작성 하지 않은 코드 였던 것 처럼 catch를 처리 하는 데 사용 됩니다. 특히 **CatchHandlerFound** exception 이벤트에 대 한 응답에 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a>반환 값  

 `HRESULT`를 반환합니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참조

- [ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스](isymunmanagedasyncmethodpropertieswriter-interface.md)
