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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3983916f56e8451e7628db3902001bd13f503114
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487930"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="85015-102">ICeeGen::GetSectionDataLen 메서드</span><span class="sxs-lookup"><span data-stu-id="85015-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="85015-103">지정된 된 섹션의 길이 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="85015-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="85015-104">이 메서드는 사용 되지 않습니다 및 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85015-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85015-105">구문</span><span class="sxs-lookup"><span data-stu-id="85015-105">Syntax</span></span>  
  
```  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85015-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="85015-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="85015-107">[in] 길이가 검색 될 데이터 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="85015-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="85015-108">[out] 반환 된 길이 지정된 된 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="85015-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85015-109">설명</span><span class="sxs-lookup"><span data-stu-id="85015-109">Remarks</span></span>  
 <span data-ttu-id="85015-110">호출 `GetSectionDataLen` 다른 메서드에서 처리 되지 않는 특수 섹션 요구 사항이 있는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="85015-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85015-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85015-111">Requirements</span></span>  
 <span data-ttu-id="85015-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="85015-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85015-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="85015-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85015-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="85015-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="85015-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85015-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85015-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="85015-116">See also</span></span>
- [<span data-ttu-id="85015-117">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85015-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
