---
title: CreateAssemblyNameObject 함수
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
ms.openlocfilehash: 00345f6c95c67f0494aa721c662f56a9e98cdd7f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108707"
---
# <a name="createassemblynameobject-function"></a>CreateAssemblyNameObject 함수
지정 된 이름을 사용 하 여 어셈블리의 고유 id를 나타내는 [IAssemblyName](iassemblyname-interface.md) 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppAssemblyNameObj`  
 제한이 반환 된 `IAssemblyName`입니다.  
  
 `szAssemblyName`  
 진행 새 `IAssemblyName` 인스턴스를 만들 어셈블리의 이름입니다.  
  
 `dwFlags`  
 진행 개체 생성자에 전달할 플래그입니다.  
  
 `pvReserved`  
 진행 향후 확장성을 위해 예약 되었습니다. `pvReserved`은 null 참조 여야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [IAssemblyName 인터페이스](iassemblyname-interface.md)
- [Fusion 전역 정적 함수](fusion-global-static-functions.md)
