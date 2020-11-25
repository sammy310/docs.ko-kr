---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod 메서드
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
ms.openlocfilehash: 2d4515087812b2b7c9303228ac5e5bbf34e8aa91
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707193"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="9d3dd-102">ISymUnmanagedAsyncMethod::GetKickoffMethod 메서드</span><span class="sxs-lookup"><span data-stu-id="9d3dd-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>

<span data-ttu-id="9d3dd-103">[DefineKickoffMethod 메서드](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d3dd-103">See [DefineKickoffMethod Method](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d3dd-104">구문</span><span class="sxs-lookup"><span data-stu-id="9d3dd-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d3dd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9d3dd-105">Parameters</span></span>  
  
|<span data-ttu-id="9d3dd-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9d3dd-106">Parameter</span></span>|<span data-ttu-id="9d3dd-107">설명</span><span class="sxs-lookup"><span data-stu-id="9d3dd-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="9d3dd-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="9d3dd-108">Return Value</span></span>  

 <span data-ttu-id="9d3dd-109">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9d3dd-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d3dd-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9d3dd-110">Requirements</span></span>  

 <span data-ttu-id="9d3dd-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="9d3dd-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d3dd-112">참조</span><span class="sxs-lookup"><span data-stu-id="9d3dd-112">See also</span></span>

- [<span data-ttu-id="9d3dd-113">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d3dd-113">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
