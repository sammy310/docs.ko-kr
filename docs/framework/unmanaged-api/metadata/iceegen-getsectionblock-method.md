---
title: ICeeGen::GetSectionBlock 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
ms.openlocfilehash: 9ce3afded5f914ecf970d8db738becc7f5cfff84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723144"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="27913-102">ICeeGen::GetSectionBlock 메서드</span><span class="sxs-lookup"><span data-stu-id="27913-102">ICeeGen::GetSectionBlock Method</span></span>

<span data-ttu-id="27913-103">코드 베이스의 섹션 블록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27913-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="27913-104">이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27913-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27913-105">구문</span><span class="sxs-lookup"><span data-stu-id="27913-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="27913-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="27913-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="27913-107">진행 코드 베이스 블록을 검색할 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="27913-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="27913-108">진행 검색할 블록의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="27913-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="27913-109">진행 블록의 첫 번째 바이트를 정렬 하는 데 사용 되는 섹션의 시작 부분을 기준으로 하는 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="27913-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="27913-110">이는 섹션 내에서 블록의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="27913-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="27913-111">제한이 검색 된 블록의 주소를 받는 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="27913-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27913-112">설명</span><span class="sxs-lookup"><span data-stu-id="27913-112">Remarks</span></span>  

 <span data-ttu-id="27913-113">`GetSectionBlock`다른 메서드에서 처리 하지 않는 특별 한 섹션 요구 사항이 있는 경우에만를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="27913-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27913-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27913-114">Requirements</span></span>  

 <span data-ttu-id="27913-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27913-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27913-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="27913-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27913-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27913-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="27913-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27913-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27913-119">참조</span><span class="sxs-lookup"><span data-stu-id="27913-119">See also</span></span>

- [<span data-ttu-id="27913-120">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27913-120">ICeeGen Interface</span></span>](iceegen-interface.md)
