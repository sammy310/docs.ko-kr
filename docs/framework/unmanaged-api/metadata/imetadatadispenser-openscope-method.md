---
description: '자세히 알아보기: IMetaDataDispenser:: OpenScope 메서드'
title: IMetaDataDispenser::OpenScope 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
ms.openlocfilehash: a1fa9a955bfc38ee4b2f23efbe8e492877a3d0c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753616"
---
# <a name="imetadatadispenseropenscope-method"></a>IMetaDataDispenser::OpenScope 메서드

기존 디스크에 있는 기존 파일을 열고 해당 메타 데이터를 메모리에 매핑합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `szScope`  
 진행 열 파일의 이름입니다. 이 파일은 CLR (공용 언어 런타임) 메타 데이터를 포함 해야 합니다.  
  
 `dwOpenFlags`  
 진행 열기에 대 한 모드 (읽기, 쓰기 등)를 지정 하는 [Coropenflags](coropenflags-enumeration.md) 열거형의 값입니다.  
  
 `riid`  
 진행 반환할 원하는 메타 데이터 인터페이스의 IID입니다. 호출자는 인터페이스를 사용 하 여 메타 데이터를 가져오거나 (읽기) 내보내기 (쓰기) 합니다.  
  
 값은 `riid` "가져오기" 또는 "내보내기" 인터페이스 중 하나를 지정 해야 합니다. 유효한 값은 IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 또는 IID_IMetaDataImport2입니다.  
  
 `ppIUnk`  
 제한이 반환 된 인터페이스에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 메타 데이터의 메모리 내 복사본은 "가져오기" 인터페이스 중 하나에서 메서드를 사용 하 여 쿼리하거나 "내보내기" 인터페이스 중 하나에서 메서드를 사용 하 여 추가할 수 있습니다.  
  
 대상 파일에 CLR 메타 데이터가 없는 경우이 메서드는 `OpenScope` 실패 합니다.  
  
 .NET Framework 버전 1.0 및 버전 1.1에서 ofRead로 설정 된 범위를 열면 `dwOpenFlags` 공유에 적합 합니다. 즉, 이전에를 호출 하 여 `OpenScope` 이전에 연 파일의 이름을 전달 하는 경우 기존 범위가 다시 사용 되며 새 데이터 구조 집합이 생성 되지 않습니다. 그러나 이러한 공유로 인해 문제가 발생할 수 있습니다.  
  
 .NET Framework 버전 2.0에서는 ofRead로 설정 된 상태에서 열린 범위가 `dwOpenFlags` 더 이상 공유 되지 않습니다. OfReadOnly 값을 사용 하 여 범위를 공유할 수 있습니다. 범위가 공유 되 면 "읽기/쓰기" 메타 데이터 인터페이스를 사용 하는 쿼리는 실패 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
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
