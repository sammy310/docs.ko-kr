---
title: ICeeGen::AllocateMethodBuffer 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.AllocateMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AllocateMethodBuffer
helpviewer_keywords:
- AllocateMethodBuffer method [.NET Framework metadata]
- ICeeGen::AllocateMethodBuffer method [.NET Framework metadata]
ms.assetid: 845ab77e-9639-47f5-99fb-f3b619e3e779
topic_type:
- apiref
ms.openlocfilehash: 34636f1ca8e42c452aa41f6145d439a26f01b0a7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436399"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="20ece-102">ICeeGen::AllocateMethodBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="20ece-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="20ece-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span><span class="sxs-lookup"><span data-stu-id="20ece-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="20ece-104">This method is obsolete and should not be used.</span><span class="sxs-lookup"><span data-stu-id="20ece-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20ece-105">구문</span><span class="sxs-lookup"><span data-stu-id="20ece-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20ece-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="20ece-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="20ece-107">[in] The length of the buffer to create.</span><span class="sxs-lookup"><span data-stu-id="20ece-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="20ece-108">[out] The returned buffer.</span><span class="sxs-lookup"><span data-stu-id="20ece-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="20ece-109">[out] The relative virtual address of the method.</span><span class="sxs-lookup"><span data-stu-id="20ece-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20ece-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="20ece-110">Requirements</span></span>  
 <span data-ttu-id="20ece-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20ece-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20ece-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="20ece-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="20ece-113">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="20ece-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="20ece-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20ece-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20ece-115">참조</span><span class="sxs-lookup"><span data-stu-id="20ece-115">See also</span></span>

- [<span data-ttu-id="20ece-116">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="20ece-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
