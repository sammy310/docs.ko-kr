---
description: '자세히 알아보기: ISymUnmanagedAsyncMethod 인터페이스'
title: ISymUnmanagedAsyncMethod 인터페이스
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: cb3120464224137dfdcff4f13ca4aee82ef4d89e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790271"
---
# <a name="isymunmanagedasyncmethod-interface"></a>ISymUnmanagedAsyncMethod 인터페이스

이 인터페이스는 [ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스](isymunmanagedasyncmethodpropertieswriter-interface.md)에 대 한 읽기 보수입니다.  
  
## <a name="syntax"></a>Syntax  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a>메서드  

 이 인터페이스에는 다음과 같은 메서드가 있습니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetAsyncStepInfo 메서드](isymunmanagedasyncmethod-getasyncstepinfo-method.md)|[DefineAsyncStepInfo 메서드](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)를 참조 하세요.|  
|[GetAsyncStepInfoCount 메서드](isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|[DefineAsyncStepInfo 메서드](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)를 참조 하세요.|  
|[GetCatchHandlerILOffset 메서드](isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|정의 [Ecatchhandleriloffset 메서드](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)를 참조 하세요.|  
|[GetKickoffMethod 메서드](isymunmanagedasyncmethod-getkickoffmethod-method.md)|[DefineKickoffMethod 메서드](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)를 참조 하세요.|  
|[HasCatchHandlerILOffset 메서드](isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|정의 [Ecatchhandleriloffset 메서드](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)를 참조 하세요.|  
|[IsAsyncMethod 메서드](isymunmanagedasyncmethod-isasyncmethod-method.md)|메서드에 비동기 정보가 있는지 여부를 확인 합니다.<br /><br /> 이 메서드가를 반환 `FALSE` 하는 경우이 인터페이스에서 다른 메서드를 호출할 수 없습니다. 이 경우 모두 반환 됩니다 `E_UNEXPECTED` .|  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** CorSym, CorSym  
  
## <a name="see-also"></a>참고 항목

- [진단 기호 저장소 인터페이스](diagnostics-symbol-store-interfaces.md)
