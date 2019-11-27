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
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="d097e-102">ICeeGen::AllocateMethodBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="d097e-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="d097e-103">메서드에 대해 지정 된 크기의 버퍼를 만들고 메서드의 상대 가상 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d097e-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="d097e-104">이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d097e-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d097e-105">구문</span><span class="sxs-lookup"><span data-stu-id="d097e-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d097e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d097e-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="d097e-107">진행 만들 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="d097e-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="d097e-108">제한이 반환 된 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="d097e-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="d097e-109">제한이 메서드의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d097e-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d097e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d097e-110">Requirements</span></span>  
 <span data-ttu-id="d097e-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d097e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d097e-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="d097e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d097e-113">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d097e-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d097e-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d097e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d097e-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d097e-115">See also</span></span>

- [<span data-ttu-id="d097e-116">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d097e-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
