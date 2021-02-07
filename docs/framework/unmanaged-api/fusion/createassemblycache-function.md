---
description: '자세한 정보: CreateAssemblyCache 함수'
title: CreateAssemblyCache 함수
ms.date: 03/30/2017
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
ms.openlocfilehash: 1646e1d33401c557b13ae5c025f53aef48042004
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761163"
---
# <a name="createassemblycache-function"></a>CreateAssemblyCache 함수

전역 어셈블리 캐시를 나타내는 새 [Iassemblycache](iassemblycache-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a>매개 변수  

 `ppAsmCache`  
 제한이 반환 된 `IAssemblyCache` 포인터입니다.  
  
 `dwReserved`  
 진행 향후 확장성을 위해 예약 되었습니다. `dwReserved` 0 이어야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IAssemblyCache 인터페이스](iassemblycache-interface.md)
- [Fusion 전역 정적 함수](fusion-global-static-functions.md)
- [전역 어셈블리 캐시](../../app-domains/gac.md)
