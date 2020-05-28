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
ms.openlocfilehash: 78b30f624bd71234e8f1b56600b3a23d15fdf517
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006035"
---
# <a name="ceesectionreloctype-enumeration"></a>CeeSectionRelocType 열거형
`reloc` [ICeeGen:: AddSectionReloc](iceegen-addsectionreloc-method.md)에 대 한 호출에서 내보낸 명령의 형식에 영향을 주는 값을 제공 합니다.  
  
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
|`srRelocAbsolute`|섹션을 기준으로 하 여 `reloc` .reloc 섹션에 아무 것도 보내지 않습니다.|  
|`srRelocHighLow`|`reloc`포인터 크기의 위치에 대해를 생성 합니다. 이는 플랫폼에 따라 BASED_HIGHLOW 또는 BASED_DIR64으로 변환 됩니다.|  
|`srRelocHighAdj`|`reloc`32 비트 숫자의 상위 16 비트에 대해를 생성 합니다. 여기서 하위 16 비트는 .reloc 테이블의 다음 단어에 포함 됩니다.|  
|`srRelocMapToken`|.Reloc 섹션에 아무 것도 보내지 않고 토큰 맵 재배치를 생성 합니다.|  
|`srRelocRelative`|값이 상대 주소 픽스업 임을 나타냅니다.|  
|`srRelocFilePos`|섹션을 기준으로 하 여 `reloc` .reloc 섹션에 아무 것도 보내지 않습니다. 섹션의 `reloc` 가상 주소가 아니라 섹션의 파일 위치를 기준으로 합니다.|  
|`srRelocCodeRelative`|코드 상대 주소 픽스업을 지정 합니다.|  
|`srRelocIA64Imm64`|`reloc`Ia64 명령에서 64 비트 주소에 대 한를 생성 `movl` 합니다.|  
|`srRelocDir64`|`reloc`64 비트 주소에 대 한를 생성 합니다.|  
|`srRelocIA64PcRel25`|`reloc`Ia64 명령의 25 비트 PC 상대 주소에 대해를 생성 `br.call` 합니다.|  
|`srRelocIA64PcRel64`|`reloc`Ia64 명령에서 64 비트 PC 상대 주소에 대해를 생성 `brl.call` 합니다.|  
|`srRelocAbsoluteTagged`|`reloc`태그가 지정 된 포인터 값에 사용 되는 30 비트 섹션 상대를 생성 합니다.|  
|`srRelocSentinel`|이 열거형에 대 한 추가를 내부 이름 배열에 반영 하는 데 도움이 되는 센티널 값 `reloc` 입니다.|  
|`srNoBaseReloc`|밑을 내보내지 않도록 지정 합니다 `reloc` .|  
|`srRelocPtr`|메모리의 미리 픽스업 콘텐츠가 섹션 오프셋이 아닌 포인터 임을 나타내는 값입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** Cor  
  
 **라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](metadata-enumerations.md)
- [ICeeGen 인터페이스](iceegen-interface.md)
- [AddSectionReloc 메서드](iceegen-addsectionreloc-method.md)
