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
ms.openlocfilehash: e1849eb95401e3637a1fd1b00715332f9886071e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715526"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="dd005-102">ICeeGen::AllocateMethodBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="dd005-102">ICeeGen::AllocateMethodBuffer Method</span></span>

<span data-ttu-id="dd005-103">메서드에 대해 지정 된 크기의 버퍼를 만들고 메서드의 상대 가상 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dd005-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="dd005-104">이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd005-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd005-105">구문</span><span class="sxs-lookup"><span data-stu-id="dd005-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (
    [in]  ULONG    cchBuffer,
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd005-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dd005-106">Parameters</span></span>  

 `cchBuffer`  
 <span data-ttu-id="dd005-107">진행 만들 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="dd005-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="dd005-108">제한이 반환 된 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="dd005-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="dd005-109">제한이 메서드의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="dd005-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd005-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dd005-110">Requirements</span></span>  

 <span data-ttu-id="dd005-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd005-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd005-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="dd005-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dd005-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd005-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dd005-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd005-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd005-115">참조</span><span class="sxs-lookup"><span data-stu-id="dd005-115">See also</span></span>

- [<span data-ttu-id="dd005-116">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dd005-116">ICeeGen Interface</span></span>](iceegen-interface.md)
