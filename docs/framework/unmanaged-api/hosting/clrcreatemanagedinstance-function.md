---
description: '자세히 알아보기: ClrCreateManagedInstance 함수'
title: ClrCreateManagedInstance 함수
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
ms.openlocfilehash: b6d3b014f54dd563e53cd8a4c48907d01945015f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799930"
---
# <a name="clrcreatemanagedinstance-function"></a>ClrCreateManagedInstance 함수

지정 된 관리 되는 형식의 인스턴스를 만듭니다.  
  
 이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다. COM 활성화를 사용 하 여 관리 되는 형식의 인스턴스를 만들거나 호스팅을 사용 합니다 ( [.NET Framework 4 및 4.5에 추가 된 CLR 호스팅 인터페이스](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)참조).  
  
## <a name="syntax"></a>구문  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pTypeName`  
 진행 요청 되는 인스턴스 형식의 이름에 대 한 포인터입니다.  
  
 `riid`  
 진행 `IID` 요청 되는 인스턴스 형식의입니다.  
  
 `ppObject`  
 제한이 호출자가 요청한 관리 되는 형식의 인스턴스에 대 한 포인터에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 공용 언어 런타임이 이미 프로세스에 로드 되어 있어야 합니다. 예를 들어 함수를 호출 하기 전에 [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 함수에 대 한 호출을 사용 하 여 로드할 수 있습니다 `ClrCreateManagedInstance` . 런타임이 로드 되지 않은 경우는 `ClrCreateManagedInstance` 먼저 런타임의 v v1.0.3705를 로드 하려고 시도 합니다. 이 작업이 실패 하면 최신 버전의 런타임을 로드 하려고 시도 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Mscoree.dll  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [사용되지 않는 CLR 호스팅 함수](deprecated-clr-hosting-functions.md)
- [호스팅](index.md)
