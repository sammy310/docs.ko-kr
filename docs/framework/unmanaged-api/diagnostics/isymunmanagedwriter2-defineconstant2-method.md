---
title: ISymUnmanagedWriter2::DefineConstant2 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineConstant2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineConstant2
helpviewer_keywords:
- DefineConstant2 method [.NET Framework debugging]
- ISymUnmanagedWriter2::DefineConstant2 method [.NET Framework debugging]
ms.assetid: dd2bc956-7dbe-49fc-a646-daa0d267f2df
topic_type:
- apiref
ms.openlocfilehash: 70ee853ff657a75dcc4df1454c4354f9d3f8202f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614723"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="d09bc-102">ISymUnmanagedWriter2::DefineConstant2 메서드</span><span class="sxs-lookup"><span data-stu-id="d09bc-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>
<span data-ttu-id="d09bc-103">상수 값의 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d09bc-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d09bc-104">구문</span><span class="sxs-lookup"><span data-stu-id="d09bc-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d09bc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d09bc-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d09bc-106">진행 상수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d09bc-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="d09bc-107">진행 상수의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d09bc-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="d09bc-108">진행 상수의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="d09bc-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d09bc-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="d09bc-109">Return Value</span></span>  
 <span data-ttu-id="d09bc-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d09bc-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d09bc-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d09bc-111">Requirements</span></span>  
 <span data-ttu-id="d09bc-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="d09bc-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d09bc-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d09bc-113">See also</span></span>

- [<span data-ttu-id="d09bc-114">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d09bc-114">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="d09bc-115">DefineConstant 메서드</span><span class="sxs-lookup"><span data-stu-id="d09bc-115">DefineConstant Method</span></span>](isymunmanagedwriter-defineconstant-method.md)
