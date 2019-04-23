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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 87dd6db9624c2216ab13e77b04cfa63f95aee7e2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183315"
---
# <a name="isymunmanagednamespace-interface"></a><span data-ttu-id="24b42-102">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="24b42-102">ISymUnmanagedNamespace Interface</span></span>
<span data-ttu-id="24b42-103">네임 스페이스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="24b42-103">Represents a namespace.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="24b42-104">메서드</span><span class="sxs-lookup"><span data-stu-id="24b42-104">Methods</span></span>  
  
|<span data-ttu-id="24b42-105">메서드</span><span class="sxs-lookup"><span data-stu-id="24b42-105">Method</span></span>|<span data-ttu-id="24b42-106">설명</span><span class="sxs-lookup"><span data-stu-id="24b42-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="24b42-107">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="24b42-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getname-method.md)|<span data-ttu-id="24b42-108">이 네임 스페이스의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="24b42-108">Gets the name of this namespace.</span></span>|  
|[<span data-ttu-id="24b42-109">GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="24b42-109">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getnamespaces-method.md)|<span data-ttu-id="24b42-110">이 네임 스페이스의 자식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="24b42-110">Gets the children of this namespace.</span></span>|  
|[<span data-ttu-id="24b42-111">GetVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="24b42-111">GetVariables Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-getvariables-method.md)|<span data-ttu-id="24b42-112">이 네임 스페이스 내에서 전역 범위에서 정의 된 모든 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="24b42-112">Returns all variables defined at global scope within this namespace.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="24b42-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="24b42-113">Requirements</span></span>  
 <span data-ttu-id="24b42-114">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="24b42-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24b42-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="24b42-115">See also</span></span>

- [<span data-ttu-id="24b42-116">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="24b42-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
