---
title: ICeeGen::AddSectionReloc 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.AddSectionReloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type:
- apiref
ms.openlocfilehash: 87a5224247c2d94613de482fbaa34bf978198bf0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715539"
---
# <a name="iceegenaddsectionreloc-method"></a>ICeeGen::AddSectionReloc 메서드

코드 베이스에 .reloc 명령을 추가 합니다.  
  
 이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a>매개 변수  

 `section`  
 진행 .Reloc 명령을 추가할 메모리 내 코드의 섹션입니다.  
  
 `offset`  
 진행 섹션의 오프셋입니다.  
  
 `relativeTo`  
 진행 가 참조 하는 섹션 `offset` 입니다.  
  
 `relocType`  
 진행 추가할 .reloc 명령의 종류를 나타내는 [CeeSectionRelocType](ceesectionreloctype-enumeration.md) 값 중 하나입니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICeeGen 인터페이스](iceegen-interface.md)
