---
title: ICeeGen::TruncateSection 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.TruncateSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::TruncateSection
helpviewer_keywords:
- TruncateSection method [.NET Framework metadata]
- ICeeGen::TruncateSection method [.NET Framework metadata]
ms.assetid: 0451d752-1e5c-4c9a-8bad-6cd35b7ba3df
topic_type:
- apiref
ms.openlocfilehash: 387f5f01f2d2589c0b34e50b69398e1feb0e77e0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008250"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="a2b2a-102">ICeeGen::TruncateSection 메서드</span><span class="sxs-lookup"><span data-stu-id="a2b2a-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="a2b2a-103">지정 된 코드 섹션을 지정 된 길이로 자릅니다.</span><span class="sxs-lookup"><span data-stu-id="a2b2a-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="a2b2a-104">이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2b2a-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2b2a-105">구문</span><span class="sxs-lookup"><span data-stu-id="a2b2a-105">Syntax</span></span>  
  
```cpp  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2b2a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a2b2a-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="a2b2a-107">진행 잘라낼 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="a2b2a-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="a2b2a-108">진행 섹션을 잘라낼 길이 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="a2b2a-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2b2a-109">설명</span><span class="sxs-lookup"><span data-stu-id="a2b2a-109">Remarks</span></span>  
 <span data-ttu-id="a2b2a-110">`TruncateSection`다른 메서드에서 처리 하지 않는 특별 한 섹션 요구 사항이 있는 경우에만를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2b2a-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2b2a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a2b2a-111">Requirements</span></span>  
 <span data-ttu-id="a2b2a-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2b2a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2b2a-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="a2b2a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a2b2a-114">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2b2a-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a2b2a-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2b2a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2b2a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2b2a-116">See also</span></span>

- [<span data-ttu-id="a2b2a-117">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a2b2a-117">ICeeGen Interface</span></span>](iceegen-interface.md)
