---
description: '자세히 알아보기: IMetaDataDispenser:: OpenScopeOnMemory 메서드'
title: IMetaDataDispenser::OpenScopeOnMemory 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
ms.openlocfilehash: 589c68ab60eec55efc43d077807789e75ae1682f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753590"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a>IMetaDataDispenser::OpenScopeOnMemory 메서드

기존 메타 데이터를 포함 하는 메모리 영역을 엽니다. 즉,이 메서드는 기존 데이터가 메타 데이터로 처리 되는 지정 된 메모리 영역을 엽니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,
    [in]  ULONG       cbData,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `pData`  
 진행 메모리 영역의 시작 주소를 지정 하는 포인터입니다.  
  
 `cbData`  
 진행 메모리 영역의 크기 (바이트)입니다.  
  
 `dwOpenFlags`  
 진행 열기에 대 한 모드 (읽기, 쓰기 등)를 지정 하는 [Coropenflags](coropenflags-enumeration.md) 열거형의 값입니다.  
  
 `riid`  
 진행 반환할 원하는 메타 데이터 인터페이스의 IID입니다. 호출자는 인터페이스를 사용 하 여 메타 데이터를 가져오거나 (읽기) 내보내기 (쓰기) 합니다.  
  
 값은 `riid` "가져오기" 또는 "내보내기" 인터페이스 중 하나를 지정 해야 합니다. 유효한 값은 IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 또는 IID_IMetaDataImport2입니다.  
  
 `ppIUnk`  
 제한이 반환 된 인터페이스에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 메타 데이터의 메모리 내 복사본은 "가져오기" 인터페이스 중 하나에서 메서드를 사용 하 여 쿼리하거나 "내보내기" 인터페이스 중 하나에서 메서드를 사용 하 여 추가할 수 있습니다.  
  
 `OpenScopeOnMemory`이 메서드는 [IMetaDataDispenser:: openscope](imetadatadispenser-openscope-method.md) 메서드와 유사 합니다. 단, 대상 메타 데이터는 디스크의 파일이 아니라 메모리에 이미 존재 합니다.  
  
 메모리의 대상 영역에 CLR (공용 언어 런타임) 메타 데이터가 포함 되어 있지 않으면 `OpenScopeOnMemory` 메서드는 실패 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [IMetaDataDispenser 인터페이스](imetadatadispenser-interface.md)
- [IMetaDataDispenserEx 인터페이스](imetadatadispenserex-interface.md)
- [IMetaDataAssemblyEmit 인터페이스](imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport 인터페이스](imetadataassemblyimport-interface.md)
- [IMetaDataEmit 인터페이스](imetadataemit-interface.md)
- [IMetaDataEmit2 인터페이스](imetadataemit2-interface.md)
- [IMetaDataImport 인터페이스](imetadataimport-interface.md)
- [IMetaDataImport2 인터페이스](imetadataimport2-interface.md)
