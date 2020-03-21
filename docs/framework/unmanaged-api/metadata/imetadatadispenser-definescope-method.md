---
title: IMetaDataDispenser::DefineScope 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.DefineScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type:
- apiref
ms.openlocfilehash: 2f9325f3795262a0c33af02f87fc5d3a020658cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177649"
---
# <a name="imetadatadispenserdefinescope-method"></a>IMetaDataDispenser::DefineScope 메서드
메모리에 새 메타데이터를 만들 수 있는 새 영역을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `rclsid`  
 【인】 만들 메타데이터 구조의 CLSID입니다. .NET Framework 버전 2.0의 경우 이 값을 CLSID_CorMetaDataRuntime.  
  
 `dwCreateFlags`  
 【인】 옵션을 지정하는 플래그입니다. .NET Framework 2.0의 경우 이 값은 0이어야 합니다.  
  
 `riid`  
 【인】 반송할 원하는 메타데이터 인터페이스의 IID; 호출자는 인터페이스를 사용하여 새 메타데이터를 만듭니다.  
  
 값은 `riid` "내각" 인터페이스 중 하나를 지정해야 합니다. 유효한 값은 IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit 또는 IID_IMetaDataEmit2.  
  
 `ppIUnk`  
 【아웃】 반환된 인터페이스에 대한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `DefineScope`메모리 내 메타데이터 테이블 집합을 만들고, 메타데이터에 대한 고유한 GUID(모듈 버전 식별자 또는 MVID)를 생성하고, 내보내지는 컴파일 유닛에 대한 모듈 테이블에 항목을 만듭니다.  
  
 적절 하 게 [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) 또는 [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) 메서드를 사용 하 여 메타 데이터 범위에 특성을 연결 할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항을](../../../../docs/framework/get-started/system-requirements.md)참조하십시오.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataDispenser 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [IMetaDataDispenserEx 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
