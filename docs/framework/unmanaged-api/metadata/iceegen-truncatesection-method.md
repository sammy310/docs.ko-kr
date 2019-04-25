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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1036d6080bf17eea288724c7980ce53dfa2121f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905673"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="e0878-102">ICeeGen::TruncateSection 메서드</span><span class="sxs-lookup"><span data-stu-id="e0878-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="e0878-103">지정 된 코드 섹션을 지정 된 길이로 자릅니다.</span><span class="sxs-lookup"><span data-stu-id="e0878-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="e0878-104">이 메서드는 사용 되지 않습니다 및 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0878-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0878-105">구문</span><span class="sxs-lookup"><span data-stu-id="e0878-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0878-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e0878-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="e0878-107">[in] 자를 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="e0878-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="e0878-108">[in] 섹션 truncate 할 바이트 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="e0878-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0878-109">설명</span><span class="sxs-lookup"><span data-stu-id="e0878-109">Remarks</span></span>  
 <span data-ttu-id="e0878-110">호출 `TruncateSection` 다른 메서드에서 처리 되지 않는 특수 섹션 요구 사항이 있는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0878-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0878-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0878-111">Requirements</span></span>  
 <span data-ttu-id="e0878-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0878-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0878-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e0878-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e0878-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="e0878-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e0878-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0878-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0878-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="e0878-116">See also</span></span>

- [<span data-ttu-id="e0878-117">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0878-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
