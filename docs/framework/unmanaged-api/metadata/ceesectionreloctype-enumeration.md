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
ms.openlocfilehash: 44a84e0752eecc1c694f3b8cf6e568b72b7d0f5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176216"
---
# <a name="ceesectionreloctype-enumeration"></a>CeeSectionRelocType 열거형
`reloc` [ICeeGen::AddSectionReloc에](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)대한 호출에서 내보낸 명령 유형에 영향을 미치는 값을 제공합니다.  
  
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
  
## <a name="members"></a>구성원  
  
|멤버|Description|  
|------------|-----------------|  
|`srRelocAbsolute`|.reloc 섹션으로 `reloc`아무 것도 보내지 는 단면 상대만 생성합니다.|  
|`srRelocHighLow`|포인터 크기의 `reloc` 위치에 대한 a를 생성합니다. 이것은 플랫폼에 따라 BASED_HIGHLOW 또는 BASED_DIR64 변환됩니다.|  
|`srRelocHighAdj`|32비트 `reloc` 숫자의 상위 16비트에 대해 a를 생성하며, 여기서 아래쪽 16비트는 .reloc 테이블의 다음 단어에 포함됩니다.|  
|`srRelocMapToken`|.reloc 섹션으로 아무 것도 보내지 않은 토큰 맵 재배치를 생성합니다.|  
|`srRelocRelative`|값이 상대 주소 수정임을 나타냅니다.|  
|`srRelocFilePos`|.reloc 섹션으로 `reloc`아무 것도 보내지 는 단면 상대만 생성합니다. 이는 `reloc` 섹션의 가상 주소가 아니라 섹션의 파일 위치를 기준으로 합니다.|  
|`srRelocCodeRelative`|코드 상대 주소 수정을 지정합니다.|  
|`srRelocIA64Imm64`|ia64 `reloc` `movl` 명령어에서 64비트 주소에 대한 a를 생성합니다.|  
|`srRelocDir64`|64비트 `reloc` 주소에 대한 a를 생성합니다.|  
|`srRelocIA64PcRel25`|ia64 `reloc` `br.call` 명령어에서 25비트 PC 상대 주소에 대한 을 생성합니다.|  
|`srRelocIA64PcRel64`|ia64 `reloc` `brl.call` 명령어에서 64비트 PC 상대 주소에 대한 a를 생성합니다.|  
|`srRelocAbsoluteTagged`|태그가 지정된 포인터 값에 `reloc`사용되는 30비트 섹션 상대값을 생성합니다.|  
|`srRelocSentinel`|이 열거형에 추가된 모든 추가 사항이 내부 `reloc` 이름 배열에 반영되도록 하는 데 도움이 되는 센티넬 값입니다.|  
|`srNoBaseReloc`|베이스를 `reloc`내보피지 않도록 지정합니다.|  
|`srRelocPtr`|메모리의 사전 수정 내용이 섹션 오프셋이 아닌 포인터임을 나타내는 값입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 코르h  
  
 **라이브러리:** MsCorEE.dll의 리소스로 포함  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [ICeeGen 인터페이스](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [AddSectionReloc 메서드](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
