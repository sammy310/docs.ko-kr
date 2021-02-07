---
description: '다음에 대 한 자세한 정보: ICeeGen:: Caaepointer 메서드'
title: ICeeGen::ComputePointer 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.ComputePointer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type:
- apiref
ms.openlocfilehash: 9319343cc93eae3e4c7b060239d23ad8aeb7d3e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721179"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="44019-103">ICeeGen::ComputePointer 메서드</span><span class="sxs-lookup"><span data-stu-id="44019-103">ICeeGen::ComputePointer Method</span></span>

<span data-ttu-id="44019-104">지정 된 코드 섹션의 버퍼를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="44019-104">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="44019-105">이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44019-105">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44019-106">구문</span><span class="sxs-lookup"><span data-stu-id="44019-106">Syntax</span></span>  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44019-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="44019-107">Parameters</span></span>  

 `section`  
 <span data-ttu-id="44019-108">진행 버퍼를 반환할 코드 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="44019-108">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="44019-109">진행 포인터를 가져올 메서드의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="44019-109">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="44019-110">제한이 반환 된 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="44019-110">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44019-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="44019-111">Requirements</span></span>  

 <span data-ttu-id="44019-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="44019-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44019-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="44019-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="44019-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44019-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="44019-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44019-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44019-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44019-116">See also</span></span>

- [<span data-ttu-id="44019-117">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="44019-117">ICeeGen Interface</span></span>](iceegen-interface.md)
