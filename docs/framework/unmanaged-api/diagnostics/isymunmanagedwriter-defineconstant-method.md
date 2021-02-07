---
description: ISymUnmanagedWriter::D efineConstant 메서드에 대해 자세히 알아보세요.
title: ISymUnmanagedWriter::DefineConstant 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineConstant
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type:
- apiref
ms.openlocfilehash: 4c3fd3986d42061272406150422f037236c4b9bf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762528"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="abcc2-103">ISymUnmanagedWriter::DefineConstant 메서드</span><span class="sxs-lookup"><span data-stu-id="abcc2-103">ISymUnmanagedWriter::DefineConstant Method</span></span>

<span data-ttu-id="abcc2-104">상수 값의 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="abcc2-104">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abcc2-105">구문</span><span class="sxs-lookup"><span data-stu-id="abcc2-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abcc2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="abcc2-106">Parameters</span></span>  

 `name`  
 <span data-ttu-id="abcc2-107">진행 상수 이름을 정의 하는에 대 한 포인터입니다 `WCHAR` .</span><span class="sxs-lookup"><span data-stu-id="abcc2-107">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="abcc2-108">진행 상수의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="abcc2-108">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="abcc2-109">[in] `signature` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="abcc2-109">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="abcc2-110">진행 상수에 대 한 형식 시그니처입니다.</span><span class="sxs-lookup"><span data-stu-id="abcc2-110">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="abcc2-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="abcc2-111">Return Value</span></span>  

 <span data-ttu-id="abcc2-112">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="abcc2-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abcc2-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="abcc2-113">Requirements</span></span>  

 <span data-ttu-id="abcc2-114">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="abcc2-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abcc2-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="abcc2-115">See also</span></span>

- [<span data-ttu-id="abcc2-116">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="abcc2-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="abcc2-117">DefineConstant2 메서드</span><span class="sxs-lookup"><span data-stu-id="abcc2-117">DefineConstant2 Method</span></span>](isymunmanagedwriter2-defineconstant2-method.md)
