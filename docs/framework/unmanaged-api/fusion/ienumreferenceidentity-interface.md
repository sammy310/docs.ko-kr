---
description: '자세히 알아보기: IEnumReferenceIdentity 인터페이스'
title: IEnumReferenceIdentity 인터페이스
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
ms.openlocfilehash: a7f17793fd737b5153c27dae59fb2aa87b46cf48
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100465303"
---
# <a name="ienumreferenceidentity-interface"></a>IEnumReferenceIdentity 인터페이스

개체의 컬렉션에 대 한 열거자 역할을 `IReferenceIdentity` 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|`IEnumReferenceIdentity`이와 동일한 멤버를 포함 하는 새에 대 한 인터페이스 포인터를 가져옵니다 `IEnumReferenceIdentity` .|  
|`IEnumReferenceIdentity::Next`|현재 위치에서 시작 하 여 지정 된 수의 `IReferenceIdentity` 개체를 가져옵니다.|  
|`IEnumReferenceIdentity::Reset`|명령 포인터를이의 시작 부분으로 이동 합니다 `IEnumReferenceIdentity` .|  
|`IEnumReferenceIdentity::Skip`|명령 포인터를 현재 위치에서 시작 하 여 지정 된 요소 수 만큼 앞으로 이동 합니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 격리. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>추가 정보

- [Fusion 인터페이스](fusion-interfaces.md)
- [IReferenceIdentity 인터페이스](ireferenceidentity-interface.md)
