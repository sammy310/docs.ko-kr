---
title: 어셈블리 위치
ms.date: 08/20/2019
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
ms.openlocfilehash: d44fb44db35b60f99583c20432c5998573298044
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107212"
---
# <a name="assembly-location"></a><span data-ttu-id="dbcb4-102">어셈블리 위치</span><span class="sxs-lookup"><span data-stu-id="dbcb4-102">Assembly location</span></span>
<span data-ttu-id="dbcb4-103">어셈블리 위치에 따라 공용 언어 런타임이 참조 시 해당 위치를 찾을 수 있는지 여부가 결정되고 어셈블리를 다른 어셈블리와 공유할 수 있는지 여부도 결정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbcb4-103">An assembly's location determines whether the common language runtime can locate it when referenced, and can also determine whether the assembly can be shared with other assemblies.</span></span> <span data-ttu-id="dbcb4-104">다음 위치에 어셈블리를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbcb4-104">You can deploy an assembly in the following locations:</span></span>  
  
- <span data-ttu-id="dbcb4-105">애플리케이션의 디렉터리 또는 하위 디렉터리.</span><span class="sxs-lookup"><span data-stu-id="dbcb4-105">The application's directory or subdirectories.</span></span>  
  
     <span data-ttu-id="dbcb4-106">어셈블리를 배포할 수 있는 가장 일반적인 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="dbcb4-106">This is the most common location for deploying an assembly.</span></span> <span data-ttu-id="dbcb4-107">애플리케이션 루트 디렉터리의 하위 디렉터리는 언어 또는 문화권에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbcb4-107">The subdirectories of an application's root directory can be based on language or culture.</span></span> <span data-ttu-id="dbcb4-108">어셈블리에 문화권 특성의 정보가 있으면 어셈블리는 애플리케이션 디렉터리 아래 하위 디렉터리에 문화권 이름과 함께 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbcb4-108">If an assembly has information in the culture attribute, it must be in a subdirectory under the application directory with that culture's name.</span></span>  
  
- <span data-ttu-id="dbcb4-109">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="dbcb4-109">The global assembly cache.</span></span>  
  
     <span data-ttu-id="dbcb4-110">공용 언어 런타임이 설치되는 모든 위치에 설치되는 컴퓨터 수준 코드 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="dbcb4-110">This is a machine-wide code cache that is installed wherever the common language runtime is installed.</span></span> <span data-ttu-id="dbcb4-111">대부분의 경우 어셈블리를 여러 애플리케이션과 공유하려고 하면 어셈블리를 전역 어셈블리 캐시에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbcb4-111">In most cases, if you intend to share an assembly with multiple applications, you should deploy it into the global assembly cache.</span></span>  
  
- <span data-ttu-id="dbcb4-112">HTTP 서버에.</span><span class="sxs-lookup"><span data-stu-id="dbcb4-112">On an HTTP server.</span></span>  
  
     <span data-ttu-id="dbcb4-113">HTTP 서버에 배포되는 어셈블리에는 강력한 이름이 있어야 합니다. 애플리케이션 구성 파일의 코드베이스 섹션에 있는 어셈블리를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="dbcb4-113">An assembly deployed on an HTTP server must have a strong name; you point to the assembly in the codebase section of the application's configuration file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbcb4-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dbcb4-114">See also</span></span>

- [<span data-ttu-id="dbcb4-115">어셈블리 만들기</span><span class="sxs-lookup"><span data-stu-id="dbcb4-115">Create assemblies</span></span>](create.md)
- [<span data-ttu-id="dbcb4-116">전역 어셈블리 캐시</span><span class="sxs-lookup"><span data-stu-id="dbcb4-116">Global assembly cache</span></span>](../../framework/app-domains/gac.md)
- [<span data-ttu-id="dbcb4-117">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="dbcb4-117">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="dbcb4-118">어셈블리를 사용한 프로그램</span><span class="sxs-lookup"><span data-stu-id="dbcb4-118">Program with assemblies</span></span>](program.md)
