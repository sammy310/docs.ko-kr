---
title: ICLRDataEnumMemoryRegionsCallback 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
ms.openlocfilehash: ddcb8064dfb9be30c66404a8762a9ca73cd6afe4
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860653"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a>ICLRDataEnumMemoryRegionsCallback 인터페이스
지정 된 메모리 영역을 열거 하려는 시도의 결과로 디버거에 보고 하는 [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) 에 대 한 콜백 메서드를 제공 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|Description|  
|------------|-----------------|  
|[EnumMemoryRegion 메서드](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|지정 된 `ICLRDataEnumMemoryRegions::EnumMemoryRegions` 메모리 영역을 열거 하려는 시도의 결과로 디버거에 보고 하기 위해에서 호출 됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** ClrData .idl, ClrData .h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
