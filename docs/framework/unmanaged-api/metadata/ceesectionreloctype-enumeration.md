---
description: '자세히 알아보기: CeeSectionRelocType 열거형'
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
ms.openlocfilehash: 49f7b39b3cc4c2e71dd3e4e426d0ca787e9ac0b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678837"
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="2b3c5-103">CeeSectionRelocType 열거형</span><span class="sxs-lookup"><span data-stu-id="2b3c5-103">CeeSectionRelocType Enumeration</span></span>

<span data-ttu-id="2b3c5-104">`reloc` [ICeeGen:: AddSectionReloc](iceegen-addsectionreloc-method.md)에 대 한 호출에서 내보낸 명령의 형식에 영향을 주는 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-104">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b3c5-105">구문</span><span class="sxs-lookup"><span data-stu-id="2b3c5-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="2b3c5-106">구성원</span><span class="sxs-lookup"><span data-stu-id="2b3c5-106">Members</span></span>  
  
|<span data-ttu-id="2b3c5-107">멤버</span><span class="sxs-lookup"><span data-stu-id="2b3c5-107">Member</span></span>|<span data-ttu-id="2b3c5-108">설명</span><span class="sxs-lookup"><span data-stu-id="2b3c5-108">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="2b3c5-109">섹션을 기준으로 하 여 `reloc` .reloc 섹션에 아무 것도 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-109">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="2b3c5-110">`reloc`포인터 크기의 위치에 대해를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-110">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="2b3c5-111">이는 플랫폼에 따라 BASED_HIGHLOW 또는 BASED_DIR64으로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-111">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="2b3c5-112">`reloc`32 비트 숫자의 상위 16 비트에 대해를 생성 합니다. 여기서 하위 16 비트는 .reloc 테이블의 다음 단어에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-112">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="2b3c5-113">.Reloc 섹션에 아무 것도 보내지 않고 토큰 맵 재배치를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-113">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="2b3c5-114">값이 상대 주소 픽스업 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-114">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="2b3c5-115">섹션을 기준으로 하 여 `reloc` .reloc 섹션에 아무 것도 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-115">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="2b3c5-116">섹션의 `reloc` 가상 주소가 아니라 섹션의 파일 위치를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-116">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="2b3c5-117">코드 상대 주소 픽스업을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-117">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="2b3c5-118">`reloc`Ia64 명령에서 64 비트 주소에 대 한를 생성 `movl` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-118">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="2b3c5-119">`reloc`64 비트 주소에 대 한를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-119">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="2b3c5-120">`reloc`Ia64 명령의 25 비트 PC 상대 주소에 대해를 생성 `br.call` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-120">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="2b3c5-121">`reloc`Ia64 명령에서 64 비트 PC 상대 주소에 대해를 생성 `brl.call` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-121">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="2b3c5-122">`reloc`태그가 지정 된 포인터 값에 사용 되는 30 비트 섹션 상대를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-122">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="2b3c5-123">이 열거형에 대 한 추가를 내부 이름 배열에 반영 하는 데 도움이 되는 센티널 값 `reloc` 입니다.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-123">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="2b3c5-124">밑을 내보내지 않도록 지정 합니다 `reloc` .</span><span class="sxs-lookup"><span data-stu-id="2b3c5-124">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="2b3c5-125">메모리의 미리 픽스업 콘텐츠가 섹션 오프셋이 아닌 포인터 임을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-125">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2b3c5-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b3c5-126">Requirements</span></span>  

 <span data-ttu-id="2b3c5-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b3c5-128">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="2b3c5-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2b3c5-129">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b3c5-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2b3c5-130">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b3c5-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b3c5-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b3c5-131">See also</span></span>

- [<span data-ttu-id="2b3c5-132">메타데이터 열거형</span><span class="sxs-lookup"><span data-stu-id="2b3c5-132">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="2b3c5-133">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b3c5-133">ICeeGen Interface</span></span>](iceegen-interface.md)
- [<span data-ttu-id="2b3c5-134">AddSectionReloc 메서드</span><span class="sxs-lookup"><span data-stu-id="2b3c5-134">AddSectionReloc Method</span></span>](iceegen-addsectionreloc-method.md)
