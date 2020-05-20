---
title: CoInitializeCor 함수
ms.date: 03/30/2017
api_name:
- CoInitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeCor
helpviewer_keywords:
- CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type:
- apiref
ms.openlocfilehash: 188f98504fa73c4a85615a4e688bae02d966b9b6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616751"
---
# <a name="coinitializecor-function"></a>CoInitializeCor 함수
`CoInitializeCor`는 사용되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a>설명  
 공용 언어 런타임을 초기화 하려면 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 또는 [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md)중 하나를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** Cor  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 전역 정적 함수](../metadata/metadata-global-static-functions.md)
