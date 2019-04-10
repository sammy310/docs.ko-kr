---
title: ISymUnmanagedVariable 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 712eca7f3f9fec9c81e638802f5a664ec6469d53
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164348"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="042e2-102">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="042e2-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="042e2-103">매개 변수, 지역 변수 또는 필드 등의 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="042e2-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="042e2-104">메서드</span><span class="sxs-lookup"><span data-stu-id="042e2-104">Methods</span></span>  
  
|<span data-ttu-id="042e2-105">메서드</span><span class="sxs-lookup"><span data-stu-id="042e2-105">Method</span></span>|<span data-ttu-id="042e2-106">설명</span><span class="sxs-lookup"><span data-stu-id="042e2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="042e2-107">GetAddressField1 메서드</span><span class="sxs-lookup"><span data-stu-id="042e2-107">GetAddressField1 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="042e2-108">이 변수에 대 한 첫 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="042e2-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="042e2-109">해당 의미는 주소에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="042e2-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="042e2-110">GetAddressField2 메서드</span><span class="sxs-lookup"><span data-stu-id="042e2-110">GetAddressField2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="042e2-111">이 변수에 대 한 두 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="042e2-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="042e2-112">해당 의미는 주소에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="042e2-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="042e2-113">GetAddressField3 메서드</span><span class="sxs-lookup"><span data-stu-id="042e2-113">GetAddressField3 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="042e2-114">이 변수에 대 한 세 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="042e2-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="042e2-115">해당 의미는 주소에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="042e2-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="042e2-116">GetAddressKind 메서드</span><span class="sxs-lookup"><span data-stu-id="042e2-116">GetAddressKind Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="042e2-117">이 변수의 주소가의 종류를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="042e2-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="042e2-118">GetAttributes 메서드</span><span class="sxs-lookup"><span data-stu-id="042e2-118">GetAttributes Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="042e2-119">이 변수에 대 한 특성 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="042e2-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="042e2-120">GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="042e2-120">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="042e2-121">부모 내에서이 변수의 끝 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="042e2-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="042e2-122">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="042e2-122">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|<span data-ttu-id="042e2-123">이 변수의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="042e2-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="042e2-124">GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="042e2-124">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="042e2-125">이 변수 시그니처를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="042e2-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="042e2-126">GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="042e2-126">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="042e2-127">부모 내에서이 변수의 시작 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="042e2-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="042e2-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="042e2-128">Requirements</span></span>  
 <span data-ttu-id="042e2-129">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="042e2-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="042e2-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="042e2-130">See also</span></span>

- [<span data-ttu-id="042e2-131">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="042e2-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
