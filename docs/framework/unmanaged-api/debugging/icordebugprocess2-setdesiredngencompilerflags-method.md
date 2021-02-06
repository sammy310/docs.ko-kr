---
description: '자세히 알아보기: ICorDebugProcess2:: SetDesiredNGENCompilerFlags 메서드'
title: ICorDebugProcess2::SetDesiredNGENCompilerFlags 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type:
- apiref
ms.openlocfilehash: 3a4749ad26e88d1a602876f28a52754323093fce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650102"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a>ICorDebugProcess2::SetDesiredNGENCompilerFlags 메서드

런타임이 해당 이미지를 현재 프로세스에 로드 하기 위해 미리 컴파일된 이미지에 포함 되어야 하는 플래그를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pdwFlags`  
 진행 올바른 미리 컴파일된 이미지를 선택 하는 데 사용 되는 컴파일러 플래그를 지정 하는 [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) 열거형의 값입니다.  
  
## <a name="remarks"></a>설명  

 `SetDesiredNGENCompilerFlags`메서드는 런타임이이 프로세스에 이미지를 로드 하도록 미리 컴파일된 이미지에 포함 되어야 하는 플래그를 지정 합니다. 이 메서드에 의해 설정 된 플래그는 올바른 미리 컴파일된 이미지를 선택 하는 데만 사용 됩니다. 이러한 이미지가 없는 경우 런타임은 MSIL (Microsoft 중간 언어) 이미지 및 JIT (just-in-time) 컴파일러를 대신 로드 합니다. 이 경우 디버거는 [ICorDebugModule2:: SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) 메서드를 사용 하 여 JIT 컴파일에 필요한 만큼 플래그를 설정 해야 합니다.  
  
 이미지가 로드 되었지만 해당 이미지에 대 한 JIT 컴파일 (이미지에 제네릭을 포함 하는 경우)이 발생 해야 하는 경우 메서드에 의해 지정 된 컴파일러 플래그가 `SetDesiredNGENCompilerFlags` 추가 JIT 컴파일에 적용 됩니다.  
  
 `SetDesiredNGENCompilerFlags` [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) 콜백 중에 메서드를 호출 해야 합니다. 나중에 메서드를 호출 하려고 하면 `SetDesiredNGENCompilerFlags` 실패 합니다. 또한 열거형에 정의 되어 있지 않거나 지정 된 프로세스에 유효 하지 않은 플래그를 설정 하려고 하면 `CorDebugJITCompilerFlags` 실패 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorDebug 인터페이스](icordebug-interface.md)
- [ICorDebugManagedCallback 인터페이스](icordebugmanagedcallback-interface.md)
