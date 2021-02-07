---
description: '자세한 정보: ICeeGen:: GetString 메서드'
title: ICeeGen::GetString 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
ms.openlocfilehash: 227b4badff3265fc22f1c76301ba03e58fea34c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706905"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="7a94b-103">ICeeGen::GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="7a94b-103">ICeeGen::GetString Method</span></span>

<span data-ttu-id="7a94b-104">지정 된 상대 가상 주소에 저장 된 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7a94b-104">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="7a94b-105">이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a94b-105">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a94b-106">구문</span><span class="sxs-lookup"><span data-stu-id="7a94b-106">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in]  ULONG      RVA,
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a94b-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7a94b-107">Parameters</span></span>  

 `RVA`  
 <span data-ttu-id="7a94b-108">진행 반환할 문자열의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7a94b-108">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="7a94b-109">제한이 반환 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7a94b-109">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a94b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7a94b-110">Requirements</span></span>  

 <span data-ttu-id="7a94b-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a94b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a94b-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="7a94b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7a94b-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a94b-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7a94b-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a94b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a94b-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a94b-115">See also</span></span>

- [<span data-ttu-id="7a94b-116">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a94b-116">ICeeGen Interface</span></span>](iceegen-interface.md)
