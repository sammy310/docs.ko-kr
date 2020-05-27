---
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
ms.openlocfilehash: b7b15261d825c1bd5f217c4cecd82ed36a716d0e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008263"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="0d832-102">ICeeGen::GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="0d832-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="0d832-103">지정 된 상대 가상 주소에 저장 된 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0d832-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="0d832-104">이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d832-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d832-105">구문</span><span class="sxs-lookup"><span data-stu-id="0d832-105">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in]  ULONG      RVA,
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d832-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0d832-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="0d832-107">진행 반환할 문자열의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="0d832-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="0d832-108">제한이 반환 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0d832-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d832-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d832-109">Requirements</span></span>  
 <span data-ttu-id="0d832-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d832-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d832-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="0d832-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d832-112">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d832-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0d832-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d832-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d832-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d832-114">See also</span></span>

- [<span data-ttu-id="0d832-115">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d832-115">ICeeGen Interface</span></span>](iceegen-interface.md)
