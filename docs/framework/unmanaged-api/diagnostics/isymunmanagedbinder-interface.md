---
title: ISymUnmanagedBinder 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder
helpviewer_keywords:
- ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e2160ad4174d9cdfe6e27d2ba7f4748bd473a5f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944226"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="6fad7-102">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6fad7-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="6fad7-103">비관리 코드에 대 한 기호 바인더를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6fad7-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6fad7-104">신뢰할 수 없는 소스에서 PDB (프로그램 데이터베이스) 파일을 여는 것은 보안상 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fad7-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6fad7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6fad7-105">Methods</span></span>  
  
|<span data-ttu-id="6fad7-106">메서드</span><span class="sxs-lookup"><span data-stu-id="6fad7-106">Method</span></span>|<span data-ttu-id="6fad7-107">설명</span><span class="sxs-lookup"><span data-stu-id="6fad7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6fad7-108">GetReaderForFile 메서드</span><span class="sxs-lookup"><span data-stu-id="6fad7-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="6fad7-109">메타 데이터 인터페이스와 파일 이름이 지정 된 경우 모듈에 연결 된 디버깅 기호를 읽을 올바른 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 구조체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fad7-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="6fad7-110">GetReaderFromStream 메서드</span><span class="sxs-lookup"><span data-stu-id="6fad7-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="6fad7-111">메타 데이터 인터페이스 및 기호 저장소를 포함 하는 스트림이 지정 된 경우 지정 된 기호 저장소에서 디버깅 기호를 읽을 올바른 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 구조체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fad7-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6fad7-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6fad7-112">Requirements</span></span>  
 <span data-ttu-id="6fad7-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6fad7-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fad7-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="6fad7-114">See also</span></span>

- [<span data-ttu-id="6fad7-115">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6fad7-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="6fad7-116">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6fad7-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="6fad7-117">ISymUnmanagedBinder3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6fad7-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
