---
description: '자세히 알아보기: ISymUnmanagedVariable 인터페이스'
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
ms.openlocfilehash: 15b6c7018f92ad4c82abb9e5b4e52bf428b3f54b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762697"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="38170-103">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38170-103">ISymUnmanagedVariable Interface</span></span>

<span data-ttu-id="38170-104">매개 변수, 지역 변수 또는 필드와 같은 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="38170-104">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="38170-105">메서드</span><span class="sxs-lookup"><span data-stu-id="38170-105">Methods</span></span>  
  
|<span data-ttu-id="38170-106">메서드</span><span class="sxs-lookup"><span data-stu-id="38170-106">Method</span></span>|<span data-ttu-id="38170-107">설명</span><span class="sxs-lookup"><span data-stu-id="38170-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38170-108">GetAddressField1 메서드</span><span class="sxs-lookup"><span data-stu-id="38170-108">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="38170-109">이 변수의 첫 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38170-109">Gets the first address field for this variable.</span></span> <span data-ttu-id="38170-110">이는 주소 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="38170-110">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="38170-111">GetAddressField2 메서드</span><span class="sxs-lookup"><span data-stu-id="38170-111">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="38170-112">이 변수의 두 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38170-112">Gets the second address field for this variable.</span></span> <span data-ttu-id="38170-113">이는 주소 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="38170-113">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="38170-114">GetAddressField3 메서드</span><span class="sxs-lookup"><span data-stu-id="38170-114">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="38170-115">이 변수의 세 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38170-115">Gets the third address field for this variable.</span></span> <span data-ttu-id="38170-116">이는 주소 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="38170-116">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="38170-117">GetAddressKind 메서드</span><span class="sxs-lookup"><span data-stu-id="38170-117">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="38170-118">이 변수의 주소 종류를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38170-118">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="38170-119">GetAttributes 메서드</span><span class="sxs-lookup"><span data-stu-id="38170-119">GetAttributes Method</span></span>](isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="38170-120">이 변수에 대 한 특성 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38170-120">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="38170-121">GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="38170-121">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="38170-122">부모 내에서이 변수의 끝 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38170-122">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="38170-123">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="38170-123">GetName Method</span></span>](isymunmanagedvariable-getname-method.md)|<span data-ttu-id="38170-124">이 변수의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38170-124">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="38170-125">GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="38170-125">GetSignature Method</span></span>](isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="38170-126">이 변수의 시그니처를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38170-126">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="38170-127">GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="38170-127">GetStartOffset Method</span></span>](isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="38170-128">부모 내에서이 변수의 시작 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38170-128">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38170-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38170-129">Requirements</span></span>  

 <span data-ttu-id="38170-130">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="38170-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38170-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38170-131">See also</span></span>

- [<span data-ttu-id="38170-132">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38170-132">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
