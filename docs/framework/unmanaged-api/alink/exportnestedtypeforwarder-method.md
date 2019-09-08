---
title: ExportNestedTypeForwarder 메서드
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb8112d6d2b5c2cbb257db2f20ff4be5a84e827b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787476"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="1f6fb-102">ExportNestedTypeForwarder 메서드</span><span class="sxs-lookup"><span data-stu-id="1f6fb-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="1f6fb-103">중첩 된 형식의 형식 전달자를 지정 된 어셈블리의 형식 테이블에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f6fb-104">구문</span><span class="sxs-lookup"><span data-stu-id="1f6fb-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f6fb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1f6fb-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1f6fb-106">내보낼 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="1f6fb-107">형식을 정의 하는 파일의 파일 토큰 또는 어셈블리 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="1f6fb-108">형식에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="1f6fb-109">부모 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="1f6fb-110">내보낼 정규화 된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1f6fb-111">`ComType``tdPublic` 또는`tdNested`와 같은 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="1f6fb-112">내보내기 유형의 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-112">Receives token of export type.</span></span> <span data-ttu-id="1f6fb-113">중첩 된 형식을 내보내는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f6fb-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="1f6fb-114">Return Value</span></span>  
 <span data-ttu-id="1f6fb-115">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f6fb-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f6fb-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f6fb-116">Requirements</span></span>  
 <span data-ttu-id="1f6fb-117">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="1f6fb-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f6fb-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="1f6fb-118">See also</span></span>

- [<span data-ttu-id="1f6fb-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f6fb-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="1f6fb-120">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f6fb-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="1f6fb-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="1f6fb-121">ALink API</span></span>](index.md)
