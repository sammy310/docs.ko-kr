---
description: '자세한 정보: ICeeGen:: EmitString 메서드'
title: ICeeGen::EmitString 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.EmitString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::EmitString
helpviewer_keywords:
- EmitString method [.NET Framework metadata]
- ICeeGen::EmitString method [.NET Framework metadata]
ms.assetid: ad2710a7-edb8-4493-8619-3fce235e3334
topic_type:
- apiref
ms.openlocfilehash: fca388d044603f932bf90a176cada6e830284702
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707113"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="08519-103">ICeeGen::EmitString 메서드</span><span class="sxs-lookup"><span data-stu-id="08519-103">ICeeGen::EmitString Method</span></span>

<span data-ttu-id="08519-104">지정 된 문자열을 코드 베이스에 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="08519-104">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="08519-105">이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08519-105">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08519-106">구문</span><span class="sxs-lookup"><span data-stu-id="08519-106">Syntax</span></span>  
  
```cpp  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08519-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="08519-107">Parameters</span></span>  

 `lpString`  
 <span data-ttu-id="08519-108">진행 내보낼 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="08519-108">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="08519-109">제한이 내보낸 문자열의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="08519-109">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08519-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08519-110">Requirements</span></span>  

 <span data-ttu-id="08519-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08519-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08519-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="08519-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08519-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08519-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08519-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08519-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08519-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08519-115">See also</span></span>

- [<span data-ttu-id="08519-116">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="08519-116">ICeeGen Interface</span></span>](iceegen-interface.md)
