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
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="95f9e-102">CeeSectionRelocType 열거형</span><span class="sxs-lookup"><span data-stu-id="95f9e-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="95f9e-103">`reloc` [ICeeGen::AddSectionReloc에](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)대한 호출에서 내보낸 명령 유형에 영향을 미치는 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="95f9e-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95f9e-104">구문</span><span class="sxs-lookup"><span data-stu-id="95f9e-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="95f9e-105">구성원</span><span class="sxs-lookup"><span data-stu-id="95f9e-105">Members</span></span>  
  
|<span data-ttu-id="95f9e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="95f9e-106">Member</span></span>|<span data-ttu-id="95f9e-107">Description</span><span class="sxs-lookup"><span data-stu-id="95f9e-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="95f9e-108">.reloc 섹션으로 `reloc`아무 것도 보내지 는 단면 상대만 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="95f9e-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="95f9e-109">포인터 크기의 `reloc` 위치에 대한 a를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="95f9e-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="95f9e-110">이것은 플랫폼에 따라 BASED_HIGHLOW 또는 BASED_DIR64 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="95f9e-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="95f9e-111">32비트 `reloc` 숫자의 상위 16비트에 대해 a를 생성하며, 여기서 아래쪽 16비트는 .reloc 테이블의 다음 단어에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="95f9e-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="95f9e-112">.reloc 섹션으로 아무 것도 보내지 않은 토큰 맵 재배치를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="95f9e-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="95f9e-113">값이 상대 주소 수정임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="95f9e-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="95f9e-114">.reloc 섹션으로 `reloc`아무 것도 보내지 는 단면 상대만 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="95f9e-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="95f9e-115">이는 `reloc` 섹션의 가상 주소가 아니라 섹션의 파일 위치를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f9e-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="95f9e-116">코드 상대 주소 수정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="95f9e-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="95f9e-117">ia64 `reloc` `movl` 명령어에서 64비트 주소에 대한 a를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="95f9e-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="95f9e-118">64비트 `reloc` 주소에 대한 a를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="95f9e-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="95f9e-119">ia64 `reloc` `br.call` 명령어에서 25비트 PC 상대 주소에 대한 을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="95f9e-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="95f9e-120">ia64 `reloc` `brl.call` 명령어에서 64비트 PC 상대 주소에 대한 a를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="95f9e-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="95f9e-121">태그가 지정된 포인터 값에 `reloc`사용되는 30비트 섹션 상대값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="95f9e-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="95f9e-122">이 열거형에 추가된 모든 추가 사항이 내부 `reloc` 이름 배열에 반영되도록 하는 데 도움이 되는 센티넬 값입니다.</span><span class="sxs-lookup"><span data-stu-id="95f9e-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="95f9e-123">베이스를 `reloc`내보피지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="95f9e-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="95f9e-124">메모리의 사전 수정 내용이 섹션 오프셋이 아닌 포인터임을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="95f9e-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95f9e-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="95f9e-125">Requirements</span></span>  
 <span data-ttu-id="95f9e-126">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95f9e-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95f9e-127">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="95f9e-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95f9e-128">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="95f9e-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="95f9e-129">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95f9e-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95f9e-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95f9e-130">See also</span></span>

- [<span data-ttu-id="95f9e-131">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="95f9e-131">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="95f9e-132">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="95f9e-132">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [<span data-ttu-id="95f9e-133">AddSectionReloc 메서드</span><span class="sxs-lookup"><span data-stu-id="95f9e-133">AddSectionReloc Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
