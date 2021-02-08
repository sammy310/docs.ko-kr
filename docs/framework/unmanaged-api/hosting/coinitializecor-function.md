---
description: '자세히 알아보기: CoInitializeCor 함수'
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
ms.openlocfilehash: e1db9914cce8a92cecf78123a2e247d75ec74acf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799852"
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

 공용 언어 런타임을 초기화 하려면 [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 또는 [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md)중 하나를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **헤더:** Cor  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 전역 정적 함수](../metadata/metadata-global-static-functions.md)
