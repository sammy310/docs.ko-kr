---
title: ICLRDataEnumMemoryRegions::EnumMemoryRegions 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
ms.openlocfilehash: f2b2bbe8bcecf71f6d3016fb35dfbf5ba1353aea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785633"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a>ICLRDataEnumMemoryRegions::EnumMemoryRegions 메서드
지정 된 메모리 영역을 열거 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `callback`  
 진행 결과를 디버거에 알리기 위해 열거 되는 각 메모리 영역에 대해이 메서드에서 호출 하는 [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) 인스턴스에 대 한 포인터입니다.  
  
 콜백이 실패를 나타내는 경우에도 메모리 영역의 열거를 계속 합니다.  
  
 `miniDumpFlags`  
 진행 사용 되지 않습니다.  
  
 `clrFlags`  
 진행 열거할 메모리 영역을 지정 하는 [Clrdataenummemoryflags](clrdataenummemoryflags-enumeration.md) 열거형의 값입니다.  
  
## <a name="remarks"></a>주의  
 이 메서드는 지정 된 [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) 인스턴스를 사용 하 여 호출자에 게 결과를 알립니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** ClrData .idl, ClrData .h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRDataEnumMemoryRegions 인터페이스](iclrdataenummemoryregions-interface.md)
