---
title: IAssemblyCacheItem 인터페이스
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type:
- apiref
ms.openlocfilehash: 72922d1fd0f8ae5e59fe76c7aa50f9c52dcd5302
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719946"
---
# <a name="iassemblycacheitem-interface"></a>IAssemblyCacheItem 인터페이스

전역 어셈블리 캐시의 단일 어셈블리를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[AbortItem 메서드](iassemblycacheitem-abortitem-method.md)|전역 어셈블리 캐시의 어셈블리가 해제 되기 전에 정리 작업을 수행할 수 있도록 허용 합니다.|  
|[Commit 메서드](iassemblycacheitem-commit-method.md)|캐시 된 어셈블리 참조를 메모리에 커밋합니다.|  
|[CreateStream 메서드](iassemblycacheitem-createstream-method.md)|지정 된 이름 및 형식을 사용 하 여 스트림을 만듭니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Fusion. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [Fusion 인터페이스](fusion-interfaces.md)
- [전역 어셈블리 캐시](../../app-domains/gac.md)
- [IAssemblyCache 인터페이스](iassemblycache-interface.md)
