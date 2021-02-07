---
description: '자세히 알아보기: ISymUnmanagedNamespace 인터페이스'
title: ISymUnmanagedNamespace 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace
helpviewer_keywords:
- ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: d42bea4e-5848-4e43-a883-69af7a313ce9
topic_type:
- apiref
ms.openlocfilehash: ff2cd2286ab006411a70ff9aa32c4f0265a73995
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709843"
---
# <a name="isymunmanagednamespace-interface"></a><span data-ttu-id="73d8f-103">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73d8f-103">ISymUnmanagedNamespace Interface</span></span>

<span data-ttu-id="73d8f-104">네임스페이스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="73d8f-104">Represents a namespace.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="73d8f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="73d8f-105">Methods</span></span>  
  
|<span data-ttu-id="73d8f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="73d8f-106">Method</span></span>|<span data-ttu-id="73d8f-107">설명</span><span class="sxs-lookup"><span data-stu-id="73d8f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="73d8f-108">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="73d8f-108">GetName Method</span></span>](isymunmanagednamespace-getname-method.md)|<span data-ttu-id="73d8f-109">이 네임 스페이스의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="73d8f-109">Gets the name of this namespace.</span></span>|  
|[<span data-ttu-id="73d8f-110">GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="73d8f-110">GetNamespaces Method</span></span>](isymunmanagednamespace-getnamespaces-method.md)|<span data-ttu-id="73d8f-111">이 네임 스페이스의 자식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="73d8f-111">Gets the children of this namespace.</span></span>|  
|[<span data-ttu-id="73d8f-112">GetVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="73d8f-112">GetVariables Method</span></span>](isymunmanagednamespace-getvariables-method.md)|<span data-ttu-id="73d8f-113">이 네임 스페이스의 전역 범위에 정의 된 모든 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="73d8f-113">Returns all variables defined at global scope within this namespace.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73d8f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="73d8f-114">Requirements</span></span>  

 <span data-ttu-id="73d8f-115">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="73d8f-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73d8f-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73d8f-116">See also</span></span>

- [<span data-ttu-id="73d8f-117">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="73d8f-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
