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
ms.openlocfilehash: 93e1f8eb17f06e42ddb243f88c593979fcb28030
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733284"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="859ec-102">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="859ec-102">ISymUnmanagedVariable Interface</span></span>

<span data-ttu-id="859ec-103">매개 변수, 지역 변수 또는 필드와 같은 변수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="859ec-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="859ec-104">메서드</span><span class="sxs-lookup"><span data-stu-id="859ec-104">Methods</span></span>  
  
|<span data-ttu-id="859ec-105">메서드</span><span class="sxs-lookup"><span data-stu-id="859ec-105">Method</span></span>|<span data-ttu-id="859ec-106">설명</span><span class="sxs-lookup"><span data-stu-id="859ec-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="859ec-107">GetAddressField1 메서드</span><span class="sxs-lookup"><span data-stu-id="859ec-107">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="859ec-108">이 변수의 첫 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="859ec-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="859ec-109">이는 주소 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="859ec-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="859ec-110">GetAddressField2 메서드</span><span class="sxs-lookup"><span data-stu-id="859ec-110">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="859ec-111">이 변수의 두 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="859ec-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="859ec-112">이는 주소 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="859ec-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="859ec-113">GetAddressField3 메서드</span><span class="sxs-lookup"><span data-stu-id="859ec-113">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="859ec-114">이 변수의 세 번째 주소 필드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="859ec-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="859ec-115">이는 주소 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="859ec-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="859ec-116">GetAddressKind 메서드</span><span class="sxs-lookup"><span data-stu-id="859ec-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="859ec-117">이 변수의 주소 종류를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="859ec-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="859ec-118">GetAttributes 메서드</span><span class="sxs-lookup"><span data-stu-id="859ec-118">GetAttributes Method</span></span>](isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="859ec-119">이 변수에 대 한 특성 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="859ec-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="859ec-120">GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="859ec-120">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="859ec-121">부모 내에서이 변수의 끝 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="859ec-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="859ec-122">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="859ec-122">GetName Method</span></span>](isymunmanagedvariable-getname-method.md)|<span data-ttu-id="859ec-123">이 변수의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="859ec-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="859ec-124">GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="859ec-124">GetSignature Method</span></span>](isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="859ec-125">이 변수의 시그니처를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="859ec-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="859ec-126">GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="859ec-126">GetStartOffset Method</span></span>](isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="859ec-127">부모 내에서이 변수의 시작 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="859ec-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="859ec-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="859ec-128">Requirements</span></span>  

 <span data-ttu-id="859ec-129">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="859ec-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="859ec-130">참조</span><span class="sxs-lookup"><span data-stu-id="859ec-130">See also</span></span>

- [<span data-ttu-id="859ec-131">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="859ec-131">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
