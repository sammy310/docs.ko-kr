---
description: '자세한 정보: ICeeGen:: Get섹션 Create 메서드'
title: ICeeGen::GetSectionCreate 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionCreate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type:
- apiref
ms.openlocfilehash: 2839d11c927dbf573f213d3ebaa9e6e6d8d5015d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706866"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="fc318-103">ICeeGen::GetSectionCreate 메서드</span><span class="sxs-lookup"><span data-stu-id="fc318-103">ICeeGen::GetSectionCreate Method</span></span>

<span data-ttu-id="fc318-104">지정 된 이름 및 플래그 값을 사용 하 여 코드 섹션을 생성 하 고 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fc318-104">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="fc318-105">이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc318-105">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc318-106">구문</span><span class="sxs-lookup"><span data-stu-id="fc318-106">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc318-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fc318-107">Parameters</span></span>  

 `name`  
 <span data-ttu-id="fc318-108">진행 만들 섹션의 이름을 지정 하는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fc318-108">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="fc318-109">진행 옵션을 지정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="fc318-109">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="fc318-110">제한이 새로 만든 코드 섹션에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fc318-110">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc318-111">설명</span><span class="sxs-lookup"><span data-stu-id="fc318-111">Remarks</span></span>  

 <span data-ttu-id="fc318-112">`GetSectionCreate`다른 메서드에서 처리 하지 않는 특별 한 섹션 요구 사항이 있는 경우에만를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc318-112">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc318-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fc318-113">Requirements</span></span>  

 <span data-ttu-id="fc318-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc318-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc318-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="fc318-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fc318-116">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc318-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fc318-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc318-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc318-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc318-118">See also</span></span>

- [<span data-ttu-id="fc318-119">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc318-119">ICeeGen Interface</span></span>](iceegen-interface.md)
