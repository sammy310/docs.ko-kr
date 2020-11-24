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
ms.openlocfilehash: d45ab56f081bf0a8802b17e338f7b404809f0f16
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683474"
---
# <a name="isymunmanagedwriter2defineconstant2-method"></a><span data-ttu-id="4b893-102">ISymUnmanagedWriter2::DefineConstant2 메서드</span><span class="sxs-lookup"><span data-stu-id="4b893-102">ISymUnmanagedWriter2::DefineConstant2 Method</span></span>

<span data-ttu-id="4b893-103">상수 값의 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b893-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b893-104">구문</span><span class="sxs-lookup"><span data-stu-id="4b893-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant2(  
    [in] const WCHAR  *name,  
    [in] VARIANT      value,  
    [in] mdSignature  sigToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b893-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4b893-105">Parameters</span></span>  

 `name`  
 <span data-ttu-id="4b893-106">진행 상수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4b893-106">[in] The constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="4b893-107">진행 상수의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4b893-107">[in] The value of the constant.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="4b893-108">진행 상수의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="4b893-108">[in] The metadata token of the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b893-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="4b893-109">Return Value</span></span>  

 <span data-ttu-id="4b893-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4b893-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b893-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4b893-111">Requirements</span></span>  

 <span data-ttu-id="4b893-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="4b893-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b893-113">참조</span><span class="sxs-lookup"><span data-stu-id="4b893-113">See also</span></span>

- [<span data-ttu-id="4b893-114">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b893-114">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="4b893-115">DefineConstant 메서드</span><span class="sxs-lookup"><span data-stu-id="4b893-115">DefineConstant Method</span></span>](isymunmanagedwriter-defineconstant-method.md)
