---
description: '자세히 알아보기: ISymUnmanagedWriter3:: OpenMethod2 메서드'
title: ISymUnmanagedWriter3::OpenMethod2 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.OpenMethod2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::OpenMethod2
helpviewer_keywords:
- ISymUnmanagedWriter3::OpenMethod2 method [.NET Framework debugging]
- OpenMethod2 method [.NET Framework debugging]
ms.assetid: 025e358c-448f-4423-a2f2-57acf437c8a5
topic_type:
- apiref
ms.openlocfilehash: 7e76be03598599a6498ed45bc3799c6d6f21e088
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761696"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="35db0-103">ISymUnmanagedWriter3::OpenMethod2 메서드</span><span class="sxs-lookup"><span data-stu-id="35db0-103">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>

<span data-ttu-id="35db0-104">메서드를 열고 이미지의 실제 섹션 오프셋을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="35db0-104">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35db0-105">구문</span><span class="sxs-lookup"><span data-stu-id="35db0-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35db0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="35db0-106">Parameters</span></span>  

 `method`  
 <span data-ttu-id="35db0-107">진행 열려는 메서드의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="35db0-107">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="35db0-108">진행 이미지의 섹션 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="35db0-108">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="35db0-109">진행 이미지의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="35db0-109">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35db0-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="35db0-110">Return Value</span></span>  

 <span data-ttu-id="35db0-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="35db0-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35db0-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="35db0-112">Requirements</span></span>  

 <span data-ttu-id="35db0-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="35db0-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35db0-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35db0-114">See also</span></span>

- [<span data-ttu-id="35db0-115">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35db0-115">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="35db0-116">OpenMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="35db0-116">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)
