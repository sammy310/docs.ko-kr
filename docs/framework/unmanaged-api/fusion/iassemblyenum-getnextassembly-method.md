---
description: '자세한 정보: IAssemblyEnum:: GetNextAssembly 메서드'
title: IAssemblyEnum::GetNextAssembly 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
ms.openlocfilehash: 52b264b1d8efad54168a6bf69fd0c715cbfa7e2a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760820"
---
# <a name="iassemblyenumgetnextassembly-method"></a>IAssemblyEnum::GetNextAssembly 메서드

이 [Iassemblyenum](iassemblyenum-interface.md) 개체에 포함 된 다음 [IAssemblyName](iassemblyname-interface.md) 에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pvReserved`  
 진행 향후 확장성을 위해 예약 되었습니다. `pvReserved` 는 null 참조 여야 합니다.  
  
 `ppName`  
 제한이 반환 된 `IAssemblyName` 포인터입니다.  
  
 `dwFlags`  
 진행 향후 확장성을 위해 예약 되었습니다. `dwFlags` 0 이어야 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IAssemblyName 인터페이스](iassemblyname-interface.md)
- [IAssemblyEnum 인터페이스](iassemblyenum-interface.md)
