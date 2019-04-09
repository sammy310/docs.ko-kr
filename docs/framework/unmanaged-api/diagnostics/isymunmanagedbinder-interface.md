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
ms.openlocfilehash: b6d91f68ac737ce28cdbef926119bb3711bc1096
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105821"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="9c5a3-102">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c5a3-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="9c5a3-103">비관리 코드의 기호 바인더를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9c5a3-104">이 신뢰할 수 없는 소스에서 프로그램 데이터베이스 (PDB) 파일을 열려면 보안 위험이 초래 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9c5a3-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9c5a3-105">Methods</span></span>  
  
|<span data-ttu-id="9c5a3-106">메서드</span><span class="sxs-lookup"><span data-stu-id="9c5a3-106">Method</span></span>|<span data-ttu-id="9c5a3-107">설명</span><span class="sxs-lookup"><span data-stu-id="9c5a3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9c5a3-108">GetReaderForFile 메서드</span><span class="sxs-lookup"><span data-stu-id="9c5a3-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="9c5a3-109">지정 된 메타 데이터 인터페이스 및 파일 이름을 올바른 반환 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 구조체는 모듈을 사용 하 여 관련 디버깅 기호를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="9c5a3-110">GetReaderFromStream 메서드</span><span class="sxs-lookup"><span data-stu-id="9c5a3-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="9c5a3-111">지정 된 메타 데이터 인터페이스 및 기호 저장소를 포함 하는 스트림을 올바른 반환 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 디버깅 읽을 구조에서 지정 된 기호 저장소 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9c5a3-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9c5a3-112">Requirements</span></span>  
 <span data-ttu-id="9c5a3-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9c5a3-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c5a3-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="9c5a3-114">See also</span></span>

- [<span data-ttu-id="9c5a3-115">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c5a3-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="9c5a3-116">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c5a3-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="9c5a3-117">ISymUnmanagedBinder3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c5a3-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
