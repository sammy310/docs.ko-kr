---
title: ISymUnmanagedBinder2 인터페이스
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2 Interface
helpviewer_keywords:
- ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type:
- apiref
ms.openlocfilehash: 8a4fbb40ec2426d000628fbd6d5f0241d3152c18
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441671"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="48933-102">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="48933-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="48933-103">비관리 코드에 대 한 기호 바인더를 나타내고 [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="48933-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="48933-104">신뢰할 수 없는 소스에서 PDB (프로그램 데이터베이스) 파일을 여는 것은 보안상 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48933-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="48933-105">메서드</span><span class="sxs-lookup"><span data-stu-id="48933-105">Methods</span></span>  
  
|<span data-ttu-id="48933-106">메서드</span><span class="sxs-lookup"><span data-stu-id="48933-106">Method</span></span>|<span data-ttu-id="48933-107">설명</span><span class="sxs-lookup"><span data-stu-id="48933-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="48933-108">GetReaderForFile2 메서드</span><span class="sxs-lookup"><span data-stu-id="48933-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="48933-109">메타 데이터 인터페이스와 파일 이름이 지정 된 경우 모듈에 연결 된 디버깅 기호를 읽을 올바른 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 인터페이스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="48933-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="48933-110">에서는 [ISymUnmanagedBinder:: GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) 메서드 보다 더 광범위 한 검색을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="48933-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="48933-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="48933-111">Requirements</span></span>  
 <span data-ttu-id="48933-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="48933-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48933-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48933-113">See also</span></span>

- [<span data-ttu-id="48933-114">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="48933-114">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="48933-115">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="48933-115">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)
- [<span data-ttu-id="48933-116">ISymUnmanagedBinder3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="48933-116">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
