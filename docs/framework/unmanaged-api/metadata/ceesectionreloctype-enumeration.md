---
title: CeeSectionRelocType 열거형
ms.date: 03/30/2017
api_name:
- CeeSectionRelocType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocType
helpviewer_keywords:
- CeeSectionRelocType enumeration [.NET Framework metadata]
ms.assetid: 124656f6-0dad-4ceb-9043-d3869ab65cde
topic_type:
- apiref
ms.openlocfilehash: efce0c13944b383c42cbff6a6af4795293ee2989
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444162"
---
# <a name="ceesectionreloctype-enumeration"></a>CeeSectionRelocType 열거형
[ICeeGen:: AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)에 대 한 호출에서 내보낸 `reloc` 명령의 형식에 영향을 주는 값을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum  {  
    srRelocAbsolute,  
    srRelocHighLow          = 3,  
    srRelocHighAdj,       
    srRelocMapToken,  
    srRelocRelative,  
    srRelocFilePos,  
    srRelocCodeRelative,  
    srRelocIA64Imm64,  
    srRelocDir64,  
    srRelocIA64PcRel25,  
    srRelocIA64PcRel64,    srRelocAbsoluteTagged,    srRelocSentinel,    srNoBaseReloc       = 0x4000,  
    srRelocPtr          = 0x8000,  
    srRelocAbsolutePtr      = srRelocPtr + srRelocAbsolute,  
    srRelocHighLowPtr       = srRelocPtr + srRelocHighLow,  
    srRelocRelativePtr      = srRelocPtr + srRelocRelative,  
    srRelocIA64Imm64Ptr     = srRelocPtr + srRelocIA64Imm64,  
    srRelocDir64Ptr         = srRelocPtr + srRelocDir64  
    } CeeSectionRelocType;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`srRelocAbsolute`|.Reloc 섹션에 아무 것도 보내지 않는 섹션 별 `reloc`를 생성 합니다.|  
|`srRelocHighLow`|포인터 크기의 위치에 대 한 `reloc`를 생성 합니다. 이는 플랫폼에 따라 BASED_HIGHLOW 또는 BASED_DIR64으로 변환 됩니다.|  
|`srRelocHighAdj`|32 비트 숫자의 상위 16 비트에 대 한 `reloc`를 생성 합니다. 여기서 하위 16 비트는 .reloc 테이블의 다음 단어에 포함 됩니다.|  
|`srRelocMapToken`|.Reloc 섹션에 아무 것도 보내지 않고 토큰 맵 재배치를 생성 합니다.|  
|`srRelocRelative`|값이 상대 주소 픽스업 임을 나타냅니다.|  
|`srRelocFilePos`|.Reloc 섹션에 아무 것도 보내지 않는 섹션 별 `reloc`를 생성 합니다. 이 `reloc` 섹션의 가상 주소가 아니라 섹션의 파일 위치를 기준으로 합니다.|  
|`srRelocCodeRelative`|코드 상대 주소 픽스업을 지정 합니다.|  
|`srRelocIA64Imm64`|Ia64 `movl` 명령에서 64 비트 주소에 대 한 `reloc`를 생성 합니다.|  
|`srRelocDir64`|64 비트 주소에 대 한 `reloc`를 생성 합니다.|  
|`srRelocIA64PcRel25`|Ia64 `br.call` 명령에서 25 비트 PC 상대 주소에 대 한 `reloc`를 생성 합니다.|  
|`srRelocIA64PcRel64`|Ia64 `brl.call` 명령에서 64 비트 PC 관련 주소에 대 한 `reloc`를 생성 합니다.|  
|`srRelocAbsoluteTagged`|태그가 지정 된 포인터 값에 사용 되는 30 비트 섹션 상대 `reloc`를 생성 합니다.|  
|`srRelocSentinel`|이 열거형에 대 한 추가 항목이 내부 `reloc` 이름 배열에 반영 되도록 하는 센티널 값입니다.|  
|`srNoBaseReloc`|기본 `reloc`를 내보내지 않도록 지정 합니다.|  
|`srRelocPtr`|메모리의 미리 픽스업 콘텐츠가 섹션 오프셋이 아닌 포인터 임을 나타내는 값입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [ICeeGen 인터페이스](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [AddSectionReloc 메서드](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
