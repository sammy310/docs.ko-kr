---
description: '자세히 알아보기: ICorProfilerInfo8:: GetDynamicFunctionInfo 메서드'
title: 'ICorProfilerInfo8:: GetDynamicFunctionInfo'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetDynamicFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: b38bd7a4f440edba0a7156176f223ba38c9807cf
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759119"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a>ICorProfilerInfo8:: GetDynamicFunctionInfo 메서드

동적 메서드에 대 한 정보를 검색 합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

## <a name="parameters"></a>매개 변수

`functionId` 진행 정보를 검색할 함수의 ID입니다.

`moduleId` 진행 함수의 부모 클래스가 정의 되어 있는 모듈에 대 한 포인터입니다.

`ppvSig` 제한이 함수의 시그니처에 대 한 포인터입니다.

`pbSig` 제한이 함수 시그니처의 바이트 수에 대 한 포인터입니다.

`cchName` 진행 배열의 최대 크기 `wszName` 입니다.

`pcchName` 제한이 배열에 있는 문자의 수 `wszName` 입니다.

`wszName` 제한이 함수 이름이 있는 경우이 배열에 해당 하는 배열입니다 `WCHAR` .

## <a name="remarks"></a>설명

IL 스텁 또는 LCG와 같은 특정 메서드에는 [IMetaDataImport](../metadata/imetadataimport-interface.md) 및 [IMetaDataImport2](../metadata/imetadataimport2-interface.md) api를 사용 하 여 검색할 수 있는 연결 된 메타 데이터가 없습니다. 이러한 메서드는 프로파일러에서 명령 포인터를 통하거나 [ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)를 수신 하 여 발견할 수 있습니다.

이 API는 사용 가능한 경우 이름을 포함 하 여 동적 메서드에 대 한 정보를 검색 하는 데 사용할 수 있습니다.

## <a name="requirements"></a>요구 사항

**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.

**헤더:** CorProf.idl, CorProf.h

**라이브러리:** CorGuids.lib

**.NET Framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>참조

- [ICorProfilerInfo8 인터페이스](icorprofilerinfo8-interface.md)
