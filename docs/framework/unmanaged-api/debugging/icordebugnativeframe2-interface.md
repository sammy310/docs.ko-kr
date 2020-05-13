---
title: ICorDebugNativeFrame2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2
helpviewer_keywords:
- ICorDebugNativeFrame2 interface [.NET Framework debugging]
ms.assetid: 52a80838-af36-4399-bc97-d8a4c6d76df2
topic_type:
- apiref
ms.openlocfilehash: cd2a2821128ad9265e8a831f7b02792e6453b1ee
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213792"
---
# <a name="icordebugnativeframe2-interface"></a>ICorDebugNativeFrame2 인터페이스
자식 및 부모 프레임 관계를 테스트하는 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[IsChild 메서드](icordebugnativeframe2-ischild-method.md)|현재 프레임이 자식 프레임 인지 여부를 확인 합니다.|  
|[IsMatchingParentFrame 메서드](icordebugnativeframe2-ismatchingparentframe-method.md)|지정 된 프레임이 현재 프레임의 부모 인지 여부를 확인 합니다.|  
|[GetStackParameterSize 메서드](icordebugnativeframe2-getstackparametersize-method.md)|X86 운영 체제의 스택에 있는 매개 변수의 누적 크기를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 "ICorDebugNativeFrame" 인터페이스를 논리적으로 확장 합니다.  
  
> [!NOTE]
> 이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
