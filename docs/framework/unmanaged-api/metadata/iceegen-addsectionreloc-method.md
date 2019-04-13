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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d50f7488c2b231ea66c12cc4903469d9e2337fb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088381"
---
# <a name="iceegenaddsectionreloc-method"></a>ICeeGen::AddSectionReloc 메서드
코드 베이스.reloc 명령을 추가합니다.  
  
 이 메서드는 사용 되지 않습니다 및 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `section`  
 [in] .Reloc 명령을 추가 하는 메모리 내 코드의 섹션입니다.  
  
 `offset`  
 [in] 섹션의 오프셋입니다.  
  
 `relativeTo`  
 [in] 섹션 `offset` 참조 합니다.  
  
 `relocType`  
 [in] 중 하나는 [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) 추가할.reloc 명령의 종류를 나타내는 값입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICeeGen 인터페이스](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
