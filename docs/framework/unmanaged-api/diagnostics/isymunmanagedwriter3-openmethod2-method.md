---
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
ms.openlocfilehash: 39235c5c26cb168dfc995de97f72b80dccb6b818
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720297"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a><span data-ttu-id="ff20e-102">ISymUnmanagedWriter3::OpenMethod2 메서드</span><span class="sxs-lookup"><span data-stu-id="ff20e-102">ISymUnmanagedWriter3::OpenMethod2 Method</span></span>

<span data-ttu-id="ff20e-103">메서드를 열고 이미지의 실제 섹션 오프셋을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff20e-103">Opens a method and provides its real section offset in the image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff20e-104">구문</span><span class="sxs-lookup"><span data-stu-id="ff20e-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenMethod2(
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff20e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff20e-105">Parameters</span></span>  

 `method`  
 <span data-ttu-id="ff20e-106">진행 열려는 메서드의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ff20e-106">[in] The metadata token for the method to be opened.</span></span>  
  
 `isect`  
 <span data-ttu-id="ff20e-107">진행 이미지의 섹션 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="ff20e-107">[in] The section offset in the image.</span></span>  
  
 `offset`  
 <span data-ttu-id="ff20e-108">진행 이미지의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="ff20e-108">[in] The offset in the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff20e-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="ff20e-109">Return Value</span></span>  

 <span data-ttu-id="ff20e-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ff20e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff20e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff20e-111">Requirements</span></span>  

 <span data-ttu-id="ff20e-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="ff20e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff20e-113">참조</span><span class="sxs-lookup"><span data-stu-id="ff20e-113">See also</span></span>

- [<span data-ttu-id="ff20e-114">ISymUnmanagedWriter3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff20e-114">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
- [<span data-ttu-id="ff20e-115">OpenMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="ff20e-115">OpenMethod Method</span></span>](isymunmanagedwriter-openmethod-method.md)
