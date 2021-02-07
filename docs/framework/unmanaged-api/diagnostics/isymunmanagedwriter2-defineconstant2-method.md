---
description: ISymUnmanagedWriter2::D efineConstant2 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 9a0c444909055e18bdcd0b54fefbc8534ff8681e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761930"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="76187-103">ISymUnmanagedWriter2::DefineConstant2 메서드</span><span class="sxs-lookup"><span data-stu-id="76187-103">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>

<span data-ttu-id="76187-104">상수 값의 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="76187-104">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76187-105">구문</span><span class="sxs-lookup"><span data-stu-id="76187-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76187-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="76187-106">Parameters</span></span>  

 `name`  
 <span data-ttu-id="76187-107">진행 상수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="76187-107">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="76187-108">진행 상수의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="76187-108">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="76187-109">진행 상수의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="76187-109">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76187-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="76187-110">Return Value</span></span>  

 <span data-ttu-id="76187-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="76187-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76187-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76187-112">Requirements</span></span>  

 <span data-ttu-id="76187-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="76187-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76187-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76187-114">See also</span></span>

- [<span data-ttu-id="76187-115">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76187-115">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="76187-116">DefineConstant 메서드</span><span class="sxs-lookup"><span data-stu-id="76187-116">DefineConstant Method</span></span>](isymunmanagedwriter-defineconstant-method.md)
