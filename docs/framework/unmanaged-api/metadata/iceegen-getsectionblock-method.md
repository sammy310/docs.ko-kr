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
ms.openlocfilehash: a494b1aaa762549528e92ab93d18929ef73eb8da
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176086"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="e4417-102">ICeeGen::GetSectionBlock 메서드</span><span class="sxs-lookup"><span data-stu-id="e4417-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="e4417-103">코드 베이스의 섹션 블록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e4417-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="e4417-104">이 메서드는 더 이상 사용되지 않으며 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4417-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4417-105">구문</span><span class="sxs-lookup"><span data-stu-id="e4417-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="e4417-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e4417-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="e4417-107">【인】 코드 베이스의 블록을 검색할 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="e4417-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="e4417-108">【인】 검색할 블록의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="e4417-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="e4417-109">【인】 블록의 첫 번째 바이트를 정렬하는 섹션의 시작 부분을 기준으로 하는 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="e4417-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="e4417-110">섹션 내의 블록 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="e4417-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="e4417-111">【아웃】 검색된 블록의 주소를 수신하는 위치에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e4417-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4417-112">설명</span><span class="sxs-lookup"><span data-stu-id="e4417-112">Remarks</span></span>  
 <span data-ttu-id="e4417-113">다른 `GetSectionBlock` 방법으로 처리되지 않는 특별한 섹션 요구 사항이 있는 경우에만 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e4417-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4417-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4417-114">Requirements</span></span>  
 <span data-ttu-id="e4417-115">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e4417-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4417-116">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="e4417-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e4417-117">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="e4417-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e4417-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4417-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4417-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4417-119">See also</span></span>

- [<span data-ttu-id="e4417-120">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4417-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
