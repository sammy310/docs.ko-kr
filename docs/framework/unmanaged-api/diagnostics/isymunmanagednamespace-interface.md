---
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
ms.openlocfilehash: d9b295060426acd7f925bcf19c05ba216fdc2a4d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707900"
---
# <a name="isymunmanagednamespace-interface"></a><span data-ttu-id="ddd68-102">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ddd68-102">ISymUnmanagedNamespace Interface</span></span>

<span data-ttu-id="ddd68-103">네임스페이스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ddd68-103">Represents a namespace.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ddd68-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ddd68-104">Methods</span></span>  
  
|<span data-ttu-id="ddd68-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ddd68-105">Method</span></span>|<span data-ttu-id="ddd68-106">설명</span><span class="sxs-lookup"><span data-stu-id="ddd68-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ddd68-107">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="ddd68-107">GetName Method</span></span>](isymunmanagednamespace-getname-method.md)|<span data-ttu-id="ddd68-108">이 네임 스페이스의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ddd68-108">Gets the name of this namespace.</span></span>|  
|[<span data-ttu-id="ddd68-109">GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="ddd68-109">GetNamespaces Method</span></span>](isymunmanagednamespace-getnamespaces-method.md)|<span data-ttu-id="ddd68-110">이 네임 스페이스의 자식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ddd68-110">Gets the children of this namespace.</span></span>|  
|[<span data-ttu-id="ddd68-111">GetVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="ddd68-111">GetVariables Method</span></span>](isymunmanagednamespace-getvariables-method.md)|<span data-ttu-id="ddd68-112">이 네임 스페이스의 전역 범위에 정의 된 모든 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddd68-112">Returns all variables defined at global scope within this namespace.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ddd68-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ddd68-113">Requirements</span></span>  

 <span data-ttu-id="ddd68-114">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="ddd68-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddd68-115">참조</span><span class="sxs-lookup"><span data-stu-id="ddd68-115">See also</span></span>

- [<span data-ttu-id="ddd68-116">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ddd68-116">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
