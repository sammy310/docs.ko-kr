---
title: ICeeGen::GetSectionDataLen 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionDataLen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionDataLen
helpviewer_keywords:
- ICeeGen::GetSectionDataLen method [.NET Framework metadata]
- GetSectionDataLen method [.NET Framework metadata]
ms.assetid: e2a06ee4-b8ee-49c7-935a-c1031a29eef2
topic_type:
- apiref
ms.openlocfilehash: 277e2584049fae397cf91281a65d05b0b49d9454
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448083"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="75934-102">ICeeGen::GetSectionDataLen 메서드</span><span class="sxs-lookup"><span data-stu-id="75934-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="75934-103">Gets the length of the specified section.</span><span class="sxs-lookup"><span data-stu-id="75934-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="75934-104">This method is obsolete and should not be used.</span><span class="sxs-lookup"><span data-stu-id="75934-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75934-105">구문</span><span class="sxs-lookup"><span data-stu-id="75934-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75934-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="75934-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="75934-107">[in] The data section whose length will be retrieved.</span><span class="sxs-lookup"><span data-stu-id="75934-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="75934-108">[out] The returned length of the specified section.</span><span class="sxs-lookup"><span data-stu-id="75934-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75934-109">주의</span><span class="sxs-lookup"><span data-stu-id="75934-109">Remarks</span></span>  
 <span data-ttu-id="75934-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span><span class="sxs-lookup"><span data-stu-id="75934-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75934-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="75934-111">Requirements</span></span>  
 <span data-ttu-id="75934-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75934-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75934-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="75934-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="75934-114">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="75934-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="75934-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75934-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75934-116">참조</span><span class="sxs-lookup"><span data-stu-id="75934-116">See also</span></span>

- [<span data-ttu-id="75934-117">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="75934-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
