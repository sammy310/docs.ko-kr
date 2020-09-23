---
title: 이 단일 인스턴스 애플리케이션을 원본 인스턴스에 연결할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_SingleInstanceCantConnect
ms.assetid: 7c2c0cee-02a1-4157-be03-39d18e18408f
ms.openlocfilehash: 8e2caa158c3874d216671979430a03b11bf60066
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095683"
---
# <a name="this-single-instance-application-could-not-connect-to-the-original-instance"></a><span data-ttu-id="81a96-102">이 단일 인스턴스 애플리케이션을 원본 인스턴스에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81a96-102">This single-instance application could not connect to the original instance</span></span>

<span data-ttu-id="81a96-103">이 단일 인스턴스 애플리케이션을 원본 인스턴스에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81a96-103">This single-instance application could not connect to the original instance.</span></span> <span data-ttu-id="81a96-104">이 문제가 발생할 수 있는 몇 가지 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="81a96-104">Some of the possible causes for this problem are as follows:</span></span>  
  
- <span data-ttu-id="81a96-105">원래 인스턴스의 응답이 중지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81a96-105">The original instance stopped responding.</span></span>  
  
- <span data-ttu-id="81a96-106">커널 개체를 만들 수 있는 권한이 애플리케이션에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81a96-106">The application does not have permissions to create kernel objects.</span></span> <span data-ttu-id="81a96-107">커널 개체에 대 한 자세한 내용은 [뮤텍스](../../standard/threading/mutexes.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="81a96-107">For more information about kernel objects, see [Mutexes](../../standard/threading/mutexes.md).</span></span>  
  
     <span data-ttu-id="81a96-108">커널 개체의 기본 이름은 어셈블리의 GUID, 주 버전 번호 및 부 버전 번호를 연결하여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="81a96-108">The base name for the kernel objects comes from concatenating the assembly's GUID, major version number, and minor version number.</span></span> <span data-ttu-id="81a96-109">예를 들어 기본 이름은 `3639f15d-9547-43da-8145-60da347829915.1`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81a96-109">For example, the base name could be `3639f15d-9547-43da-8145-60da347829915.1`.</span></span>  
  
## <a name="to-correct-this-error-when-developing-the-application"></a><span data-ttu-id="81a96-110">애플리케이션을 개발할 때 이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="81a96-110">To correct this error when developing the application</span></span>  
  
1. <span data-ttu-id="81a96-111">애플리케이션이 응답하지 않는 상태로 전환되지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="81a96-111">Check that the application does not go into an unresponsive state.</span></span>  
  
2. <span data-ttu-id="81a96-112">애플리케이션에 커널 개체를 만들 수 있는 권한이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="81a96-112">Check that the application has sufficient permissions to create kernel objects.</span></span>  
  
3. <span data-ttu-id="81a96-113">애플리케이션의 원래 인스턴스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="81a96-113">Restart the original instance of the application.</span></span>  
  
4. <span data-ttu-id="81a96-114">컴퓨터를 다시 시작하여 원래 인스턴스 애플리케이션에 연결하는 데 필요한 리소스를 사용 중일 수 있는 프로세스를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="81a96-114">Restart the computer to clear any process that may be using the resource that is required to connect to the original instance application.</span></span>  
  
5. <span data-ttu-id="81a96-115">오류가 발생한 상황을 파악하여 Microsoft 기술 지원 서비스에 전화로 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="81a96-115">Note the circumstances under which the error occurred, and telephone Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81a96-116">참조</span><span class="sxs-lookup"><span data-stu-id="81a96-116">See also</span></span>

- [<span data-ttu-id="81a96-117">디버거 기본 사항</span><span class="sxs-lookup"><span data-stu-id="81a96-117">Debugger Basics</span></span>](/visualstudio/debugger/debugger-feature-tour)
