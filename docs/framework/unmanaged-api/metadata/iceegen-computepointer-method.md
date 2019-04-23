---
title: ICeeGen::ComputePointer 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.ComputePointer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 79ef272e0c8afa0cd1942416c3a5eb9b825c2e6f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145147"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="1e7b7-102">ICeeGen::ComputePointer 메서드</span><span class="sxs-lookup"><span data-stu-id="1e7b7-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="1e7b7-103">지정 된 코드 섹션에 대 한 버퍼를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e7b7-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="1e7b7-104">이 메서드는 사용 되지 않습니다 및 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e7b7-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e7b7-105">구문</span><span class="sxs-lookup"><span data-stu-id="1e7b7-105">Syntax</span></span>  
  
```  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e7b7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1e7b7-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="1e7b7-107">[in] 버퍼를 반환 하는 코드 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="1e7b7-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="1e7b7-108">[in] 에 대 한 포인터를 가져올 메서드의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1e7b7-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="1e7b7-109">[out] 반환 된 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1e7b7-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e7b7-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1e7b7-110">Requirements</span></span>  
 <span data-ttu-id="1e7b7-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1e7b7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e7b7-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1e7b7-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1e7b7-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="1e7b7-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1e7b7-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e7b7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e7b7-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="1e7b7-115">See also</span></span>

- [<span data-ttu-id="1e7b7-116">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1e7b7-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
