---
title: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type:
- apiref
ms.openlocfilehash: c8313b7c97eb5d94424259dc91459f62e13368fb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785600"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a>ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion 메서드
지정 된 메모리 영역을 열거 하려는 시도의 결과로 디버거에 보고 하기 위해 [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) 에 의해 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `address`  
 진행 열거할 메모리 영역의 시작 주소입니다.  
  
 `size`  
 진행 메모리 영역의 크기 (바이트)입니다.  
  
## <a name="remarks"></a>주의  
 `ICLRDataEnumMemoryRegions::EnumMemoryRegions` 메서드는 각 메모리 영역을 열거 하려고 시도한 후이 콜백 메서드를 호출 합니다. 열거형은이 메서드가 실패를 나타내는 HRESULT를 반환 하는 경우에도 계속 됩니다.  
  
 이 콜백에서 보고 한 지역은 중복 되거나 중복 된 지역이 될 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** ClrData .idl, ClrData .h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICLRDataEnumMemoryRegionsCallback 인터페이스](iclrdataenummemoryregionscallback-interface.md)
