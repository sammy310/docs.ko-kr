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
ms.openlocfilehash: 554e59484f00626726f7f024c69e93a5e6647130
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727382"
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="5c60f-102">ISymUnmanagedBinder 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c60f-102">ISymUnmanagedBinder Interface</span></span>

<span data-ttu-id="5c60f-103">비관리 코드의 기호 바인더를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5c60f-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5c60f-104">신뢰할 수 없는 소스에서 PDB (프로그램 데이터베이스) 파일을 여는 것은 보안상 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c60f-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5c60f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5c60f-105">Methods</span></span>  
  
|<span data-ttu-id="5c60f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="5c60f-106">Method</span></span>|<span data-ttu-id="5c60f-107">설명</span><span class="sxs-lookup"><span data-stu-id="5c60f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5c60f-108">GetReaderForFile 메서드</span><span class="sxs-lookup"><span data-stu-id="5c60f-108">GetReaderForFile Method</span></span>](isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="5c60f-109">메타 데이터 인터페이스와 파일 이름이 지정 된 경우 모듈에 연결 된 디버깅 기호를 읽을 올바른 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 구조체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c60f-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="5c60f-110">GetReaderFromStream 메서드</span><span class="sxs-lookup"><span data-stu-id="5c60f-110">GetReaderFromStream Method</span></span>](isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="5c60f-111">메타 데이터 인터페이스 및 기호 저장소를 포함 하는 스트림이 지정 된 경우 지정 된 기호 저장소에서 디버깅 기호를 읽을 올바른 [ISymUnmanagedReader](isymunmanagedreader-interface.md) 구조체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c60f-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5c60f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c60f-112">Requirements</span></span>  

 <span data-ttu-id="5c60f-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="5c60f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c60f-114">참조</span><span class="sxs-lookup"><span data-stu-id="5c60f-114">See also</span></span>

- [<span data-ttu-id="5c60f-115">진단 기호 저장소 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c60f-115">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="5c60f-116">ISymUnmanagedBinder2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c60f-116">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="5c60f-117">ISymUnmanagedBinder3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c60f-117">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)
