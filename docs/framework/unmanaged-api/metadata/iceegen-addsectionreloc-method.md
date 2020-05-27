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
ms.openlocfilehash: 2f66d34fcfdd8c61dcc92817ec1a928ac5b603fc
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008900"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="bdbc8-102">ICeeGen::AddSectionReloc 메서드</span><span class="sxs-lookup"><span data-stu-id="bdbc8-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="bdbc8-103">코드 베이스에 .reloc 명령을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="bdbc8-104">이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdbc8-105">구문</span><span class="sxs-lookup"><span data-stu-id="bdbc8-105">Syntax</span></span>  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdbc8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bdbc8-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="bdbc8-107">진행 .Reloc 명령을 추가할 메모리 내 코드의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="bdbc8-108">진행 섹션의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="bdbc8-109">진행 가 참조 하는 섹션 `offset` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="bdbc8-110">진행 추가할 .reloc 명령의 종류를 나타내는 [CeeSectionRelocType](ceesectionreloctype-enumeration.md) 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-110">[in] One of the [CeeSectionRelocType](ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdbc8-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bdbc8-111">Requirements</span></span>  
 <span data-ttu-id="bdbc8-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdbc8-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="bdbc8-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bdbc8-114">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdbc8-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bdbc8-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdbc8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdbc8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bdbc8-116">See also</span></span>

- [<span data-ttu-id="bdbc8-117">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bdbc8-117">ICeeGen Interface</span></span>](iceegen-interface.md)
