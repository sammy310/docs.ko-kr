---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 메서드
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: 103fe1b6845edfe0a364db979557db63511f6ee3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130379"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a>ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 메서드

지정 된 NGen 모듈에 정의 되어 있고 지정 된 메서드를 인라인 하는 모든 메서드에 대 한 열거자를 반환 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a>매개 변수

`inlinersModuleId`\
진행 NGen 모듈의 식별자입니다.

`inlineeModuleId`\
진행 `inlineeMethodId`를 정의 하는 모듈의 식별자입니다. 자세한 내용은 설명 부분을 참조하세요.

`inlineeMethodId`\
진행 인라인 된 메서드의 식별자입니다. 자세한 내용은 설명 부분을 참조하세요.

`incompleteData`\
제한이 `ppEnum` 지정 된 메서드를 인라인 하는 모든 메서드를 포함 하는지 여부를 나타내는 플래그입니다.  자세한 내용은 설명 부분을 참조하세요.

`ppEnum`\
제한이 열거자의 주소에 대 한 포인터입니다.

## <a name="remarks"></a>주의

`inlineeModuleId` 및 `inlineeMethodId` 함께 인라인 될 수 있는 메서드의 전체 식별자를 형성 합니다. 예를 들어 모듈 `A` `Simple.Add`메서드를 정의 한다고 가정 합니다.

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

및 모듈 B는 `Fancy.AddTwice`을 정의 합니다.

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

에서는 `Fancy.AddTwice`이 `SimpleAdd`에 대 한 호출을 inlines 한다고 가정 합니다. 프로파일러에서는이 열거자를 사용 하 여 `Simple.Add`인라인 된 모듈 B에 정의 된 모든 메서드를 찾을 수 있으며, 결과는 `AddTwice`를 열거 합니다.  `inlineeModuleId`는 모듈 `A`의 식별자 이며 `inlineeMethodId`는 `Simple.Add(int a, int b)`의 식별자입니다.

함수가 반환 된 후 `incompleteData` true 이면 열거자에 지정 된 메서드를 인라인 하는 메서드가 모두 포함 되지 않습니다. Inliners 모듈의 직접 또는 간접 종속성이 하나 이상 아직 로드 되지 않은 경우이 문제가 발생할 수 있습니다. 프로파일러가 정확한 데이터를 필요로 하는 경우에는 나중에 각 모듈 로드에서 더 많은 모듈이 로드 될 때 다시 시도해 야 합니다.

`EnumNgenModuleMethodsInliningThisMethod` 메서드를 사용 하 여 ReJIT의 인라인에 대 한 제한 사항을 해결할 수 있습니다. ReJIT를 사용 하면 프로파일러가 메서드 구현을 변경한 다음 즉석에서 새 코드를 만들 수 있습니다. 예를 들어 다음과 같이 `Simple.Add`를 변경할 수 있습니다.

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

그러나 `Fancy.AddTwice` 이미 `Simple.Add`인라인 되어 있기 때문에 이전과 같은 동작이 계속 됩니다. 이 제한을 해결 하기 위해 호출자는 `Simple.Add` 인라인 하는 모든 모듈의 모든 메서드를 검색 하 고 이러한 각 메서드에서 `ICorProfilerInfo5::RequestRejit`를 사용 해야 합니다. 메서드를 다시 컴파일하면 이전 동작 대신 `Simple.Add`의 새 동작이 발생 합니다.

## <a name="requirements"></a>요구 사항

**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.

**헤더:** CorProf.idl, CorProf.h

**라이브러리:** CorGuids.lib

**.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]

## <a name="see-also"></a>참조

- [ICorProfilerInfo6 인터페이스](icorprofilerinfo6-interface.md)
