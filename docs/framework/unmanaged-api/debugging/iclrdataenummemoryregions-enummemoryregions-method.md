---
description: '자세히 알아보기: ICLRDataEnumMemoryRegions:: EnumMemoryRegions 메서드'
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
ms.openlocfilehash: 48887defab38d6ac99c718e14646d39166927438
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785733"
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
  
## <a name="remarks"></a>설명  

 이 메서드는 지정 된 [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) 인스턴스를 사용 하 여 호출자에 게 결과를 알립니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** ClrData .idl, ClrData .h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [ICLRDataEnumMemoryRegions 인터페이스](iclrdataenummemoryregions-interface.md)
