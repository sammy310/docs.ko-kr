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
ms.openlocfilehash: b45b0a59a29a27e7b0a395f3928215959450f9a5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698470"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="40e34-102">ICeeGen::GetSectionDataLen 메서드</span><span class="sxs-lookup"><span data-stu-id="40e34-102">ICeeGen::GetSectionDataLen Method</span></span>

<span data-ttu-id="40e34-103">지정 된 섹션의 길이를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="40e34-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="40e34-104">이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40e34-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40e34-105">구문</span><span class="sxs-lookup"><span data-stu-id="40e34-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40e34-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="40e34-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="40e34-107">진행 길이가 검색 되는 데이터 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="40e34-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="40e34-108">제한이 지정 된 섹션의 반환 된 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="40e34-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40e34-109">설명</span><span class="sxs-lookup"><span data-stu-id="40e34-109">Remarks</span></span>  

 <span data-ttu-id="40e34-110">`GetSectionDataLen`다른 메서드에서 처리 하지 않는 특별 한 섹션 요구 사항이 있는 경우에만를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="40e34-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40e34-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="40e34-111">Requirements</span></span>  

 <span data-ttu-id="40e34-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40e34-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40e34-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="40e34-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="40e34-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40e34-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="40e34-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40e34-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40e34-116">참조</span><span class="sxs-lookup"><span data-stu-id="40e34-116">See also</span></span>

- [<span data-ttu-id="40e34-117">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="40e34-117">ICeeGen Interface</span></span>](iceegen-interface.md)
