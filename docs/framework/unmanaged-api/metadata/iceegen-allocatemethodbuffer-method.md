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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7be1bd2934fbb2e09a39c3042fa9ae314e89d629
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905608"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="bd54b-102">ICeeGen::AllocateMethodBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="bd54b-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="bd54b-103">메서드의 경우 지정된 된 크기의 버퍼를 만들고 메서드의 상대 가상 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bd54b-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="bd54b-104">이 메서드는 사용 되지 않습니다 및 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd54b-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd54b-105">구문</span><span class="sxs-lookup"><span data-stu-id="bd54b-105">Syntax</span></span>  
  
```  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd54b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bd54b-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="bd54b-107">[in] 만들 버퍼의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="bd54b-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="bd54b-108">[out] 반환 된 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="bd54b-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="bd54b-109">[out] 메서드의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="bd54b-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd54b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd54b-110">Requirements</span></span>  
 <span data-ttu-id="bd54b-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bd54b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd54b-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bd54b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd54b-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="bd54b-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd54b-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd54b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd54b-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="bd54b-115">See also</span></span>

- [<span data-ttu-id="bd54b-116">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bd54b-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
