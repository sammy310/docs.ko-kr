---
title: ICorPublish::EnumProcesses 메서드
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
ms.openlocfilehash: 70255a89cee13abfe63b01351f8ffba51e54665a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396397"
---
# <a name="icorpublishenumprocesses-method"></a>ICorPublish::EnumProcesses 메서드
이 컴퓨터에서 실행 되는 관리 되는 프로세스의 열거자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `Type`  
 검색할 프로세스의 유형을 지정 하는 [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) 열거형의 값입니다. 현재 버전에서는 COR_PUB_MANAGEDONLY만 유효 합니다.  
  
 `ppIEnum`  
 프로세스의 열거자 인 [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) 인스턴스의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 열거자의 프로세스 컬렉션은 메서드가 호출 될 때 실행 중인 프로세스의 스냅숏을 기반으로 합니다 `EnumProcesses` . 열거자는가 호출 된 후에 종료 되거나 시작 되는 프로세스를 포함 하지 않습니다 `EnumProcesses` .  
  
 `EnumProcesses`이 [ICorPublish](icorpublish-interface.md) 인스턴스에서 메서드를 두 번 이상 호출 하 여 새로운 최신 프로세스 컬렉션을 만들 수 있습니다. 기존 컬렉션은 메서드에 대 한 후속 호출의 영향을 받지 않습니다 `EnumProcesses` .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorPub .idl, CorPub. h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorPublish 인터페이스](icorpublish-interface.md)
