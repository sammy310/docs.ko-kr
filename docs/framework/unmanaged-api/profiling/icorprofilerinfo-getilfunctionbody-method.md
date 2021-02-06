---
description: '자세히 알아보기: ICorProfilerInfo:: GetILFunctionBody 메서드'
title: ICorProfilerInfo::GetILFunctionBody 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
ms.openlocfilehash: 7294592d1a2747dc10f44d1206561a9a1662ce7b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647481"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a>ICorProfilerInfo::GetILFunctionBody 메서드

MSIL (Microsoft 중간 언어) 코드에서 헤더를 시작 하는 메서드의 본문에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a>매개 변수  

 `moduleId`  
 진행 함수가 상주 하는 모듈의 ID입니다.  
  
 `methodId`  
 진행 메서드에 대 한 메타 데이터 토큰입니다.  
  
 `ppMethodHeader`  
 제한이 메서드의 헤더에 대 한 포인터입니다.  
  
 `pcbMethodSize`  
 제한이 메서드의 크기를 지정 하는 정수입니다.  
  
## <a name="remarks"></a>설명  

 메서드는 해당 메서드가 상주 하는 모듈로 범위가 지정 됩니다. 메서드는 `GetILFunctionBody` CLR (공용 언어 런타임)에 의해 로드 되기 전에 도구에 MSIL 코드에 대 한 액세스를 제공 하도록 설계 되었으므로 메서드의 메타 데이터 토큰을 사용 하 여 원하는 인스턴스를 찾습니다.  
  
 `GetILFunctionBody` 는가 `methodId` MSIL 코드 (예: 추상 메서드 또는 플랫폼 호출 (PInvoke) 메서드)를 사용 하지 않고 메서드를 가리키는 경우 CORPROF_E_FUNCTION_NOT_IL HRESULT를 반환할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICorProfilerInfo 인터페이스](icorprofilerinfo-interface.md)
