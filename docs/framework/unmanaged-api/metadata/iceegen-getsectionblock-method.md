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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e600f29a9036bb28031bd7854bc8cbb34c4566a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905491"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="0bf88-102">ICeeGen::GetSectionBlock 메서드</span><span class="sxs-lookup"><span data-stu-id="0bf88-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="0bf88-103">코드 베이스의 섹션에서는 블록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0bf88-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="0bf88-104">이 메서드는 사용 되지 않습니다 및 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bf88-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bf88-105">구문</span><span class="sxs-lookup"><span data-stu-id="0bf88-105">Syntax</span></span>  
  
```  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,     
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="0bf88-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0bf88-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="0bf88-107">[in] 블록의 코드 베이스를 검색할 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="0bf88-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="0bf88-108">[in] 검색할 블록의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="0bf88-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="0bf88-109">[in] 블록의 첫 번째 바이트에 맞출 수 있는 섹션의 시작을 기준으로 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="0bf88-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="0bf88-110">이 섹션에서 블록의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="0bf88-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="0bf88-111">[out] 검색 된 블록의 주소를 수신 하는 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0bf88-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bf88-112">설명</span><span class="sxs-lookup"><span data-stu-id="0bf88-112">Remarks</span></span>  
 <span data-ttu-id="0bf88-113">호출 `GetSectionBlock` 다른 메서드에서 처리 되지 않는 특수 섹션 요구 사항이 있는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bf88-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bf88-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0bf88-114">Requirements</span></span>  
 <span data-ttu-id="0bf88-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0bf88-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bf88-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0bf88-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0bf88-117">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="0bf88-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0bf88-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bf88-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bf88-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="0bf88-119">See also</span></span>

- [<span data-ttu-id="0bf88-120">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0bf88-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
