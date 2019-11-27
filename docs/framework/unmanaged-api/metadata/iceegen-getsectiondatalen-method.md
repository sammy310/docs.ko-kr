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
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="6553d-102">ICeeGen::GetSectionDataLen 메서드</span><span class="sxs-lookup"><span data-stu-id="6553d-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="6553d-103">지정 된 섹션의 길이를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6553d-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="6553d-104">이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6553d-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6553d-105">구문</span><span class="sxs-lookup"><span data-stu-id="6553d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6553d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6553d-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="6553d-107">진행 길이가 검색 되는 데이터 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="6553d-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="6553d-108">제한이 지정 된 섹션의 반환 된 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="6553d-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6553d-109">설명</span><span class="sxs-lookup"><span data-stu-id="6553d-109">Remarks</span></span>  
 <span data-ttu-id="6553d-110">다른 메서드에서 처리 하지 않는 특별 한 섹션 요구 사항이 있는 경우에만 `GetSectionDataLen`를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6553d-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6553d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6553d-111">Requirements</span></span>  
 <span data-ttu-id="6553d-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6553d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6553d-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="6553d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6553d-114">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6553d-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6553d-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6553d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6553d-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="6553d-116">See also</span></span>

- [<span data-ttu-id="6553d-117">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6553d-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
