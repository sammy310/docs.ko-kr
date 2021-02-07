---
description: '자세히 알아보기: ICorDebugModule:: GetMetaDataInterface 메서드'
title: ICorDebugModule::GetMetaDataInterface 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type:
- apiref
ms.openlocfilehash: 39af2560b4c10f6dc490bfba5425e2339a7c1823
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691643"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a>ICorDebugModule::GetMetaDataInterface 메서드

모듈에 대 한 메타 데이터를 검사 하는 데 사용할 수 있는 메타 데이터 인터페이스 개체를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `riid`  
 진행 메타 데이터 인터페이스를 지정 하는 참조 ID입니다.  
  
 `ppObj`  
 제한이 `T:IUnknown` [메타 데이터 인터페이스](../metadata/metadata-interfaces.md)중 하나인 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  

 디버거는 메서드를 사용 하 여 `GetMetaDataInterface` 모듈에 대 한 원래 메타 데이터의 복사본을 만들 수 있습니다 .이 경우 해당 모듈을 편집 하기 위해이 작업을 수행 해야 합니다. 디버거는 `GetMetaDataInterface` 를 호출 하 여 모듈에 대 한 [IMetaDataEmit](../metadata/imetadataemit-interface.md) interface 개체를 가져온 다음 [IMetaDataEmit:: SaveToMemory](../metadata/imetadataemit-savetomemory-method.md) 를 호출 하 여 모듈의 메타 데이터 복사본을 메모리에 저장 합니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터](../metadata/index.md)
