---
title: ISymUnmanagedBinder3 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a6f514cc070a0a38eb09a5387efc8611100765b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944106"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="149ab-102">ISymUnmanagedBinder3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="149ab-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="149ab-103">기호 바인더 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="149ab-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="149ab-104">인터페이스를 `QueryInterface` `ISymUnmanagedBinder` 구현 하는 개체에서를 호출 하 여이 인터페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="149ab-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="149ab-105">신뢰할 수 없는 소스에서 PDB (프로그램 데이터베이스) 파일을 여는 것은 보안상 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="149ab-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="149ab-106">메서드</span><span class="sxs-lookup"><span data-stu-id="149ab-106">Methods</span></span>  
  
|<span data-ttu-id="149ab-107">메서드</span><span class="sxs-lookup"><span data-stu-id="149ab-107">Method</span></span>|<span data-ttu-id="149ab-108">Description</span><span class="sxs-lookup"><span data-stu-id="149ab-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="149ab-109">GetReaderFromCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="149ab-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="149ab-110">사용자가 `IID_IDiaReadExeAtRVACallback` 또는 `IID_IDiaReadExeAtOffsetCallback` 를 사용 하 여를 구현 하거나 제공 하 여 메모리에서 디버그 디렉터리 정보를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="149ab-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="149ab-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="149ab-111">Requirements</span></span>  
 <span data-ttu-id="149ab-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="149ab-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="149ab-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="149ab-113">See also</span></span>

- [<span data-ttu-id="149ab-114">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="149ab-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="149ab-115">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="149ab-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="149ab-116">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="149ab-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
