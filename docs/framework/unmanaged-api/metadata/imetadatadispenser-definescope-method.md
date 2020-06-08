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
ms.openlocfilehash: 12a32b5d2f0647ea2d9b696d08d6644e30be0c65
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501367"
---
# <a name="imetadatadispenserdefinescope-method"></a>IMetaDataDispenser::DefineScope 메서드
새 메타 데이터를 만들 수 있는 메모리에 새 영역을 만듭니다.  
  
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
 진행 만들 메타 데이터 구조 버전의 CLSID입니다. .NET Framework 버전 2.0에 대해이 값을 CLSID_CorMetaDataRuntime 해야 합니다.  
  
 `dwCreateFlags`  
 진행 옵션을 지정 하는 플래그입니다. .NET Framework 2.0의 경우이 값은 0 이어야 합니다.  
  
 `riid`  
 진행 반환할 원하는 메타 데이터 인터페이스의 IID입니다. 호출자는 인터페이스를 사용 하 여 새 메타 데이터를 만듭니다.  
  
 값은 `riid` "내보내기" 인터페이스 중 하나를 지정 해야 합니다. 유효한 값은 IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit 또는 IID_IMetaDataEmit2입니다.  
  
 `ppIUnk`  
 제한이 반환 된 인터페이스에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `DefineScope`는 메모리 내 메타 데이터 테이블 집합을 만들고, 메타 데이터에 대 한 고유 GUID (모듈 버전 식별자 또는 MVID)를 생성 하 고, 내보내는 컴파일 단위에 대 한 모듈 테이블에 항목을 만듭니다.  
  
 [IMetaDataEmit:: SetModuleProps](imetadataemit-setmoduleprops-method.md) 또는 [IMetaDataEmit::D efinecustomattribute](imetadataemit-definecustomattribute-method.md) 메서드를 적절 하 게 사용 하 여 전체 메타 데이터 범위에 특성을 연결할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataDispenser 인터페이스](imetadatadispenser-interface.md)
- [IMetaDataDispenserEx 인터페이스](imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit 인터페이스](imetadataassemblyemit-interface.md)
- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
