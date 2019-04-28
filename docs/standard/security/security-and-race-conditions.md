---
title: 보안 및 경합 상태
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], race conditions
- race conditions
- secure coding, race conditions
- code security, race conditions
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 57ceaedc7c38ae70a0db5a7fd584a765a7474aff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61933811"
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="86803-102">보안 및 경합 상태</span><span class="sxs-lookup"><span data-stu-id="86803-102">Security and Race Conditions</span></span>
<span data-ttu-id="86803-103">다른 문제 영역을 보안 허점을 경합 상태에 의해 악용 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86803-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="86803-104">여러 가지 방법으로이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86803-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="86803-105">다음에 나오는 하위 항목은 개발자가 피해 야 하는 주요 문제 중 일부를 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="86803-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="86803-106">Dispose 메서드에서 경합</span><span class="sxs-lookup"><span data-stu-id="86803-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="86803-107">클래스의 경우 **Dispose** 메서드 (자세한 내용은 참조 하세요. [가비지 수집](../../../docs/standard/garbage-collection/index.md))은 동기화 되지 않은 것 같습니다 내부 정리 코드 **Dispose** 실행할 수 있습니다 둘 다음 예제에서와 같이 번입니다.</span><span class="sxs-lookup"><span data-stu-id="86803-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
```vb  
Sub Dispose()  
    If Not (myObj Is Nothing) Then  
       Cleanup(myObj)  
       myObj = Nothing  
    End If  
End Sub  
```  
  
```csharp  
void Dispose()   
{  
    if (myObj != null)   
    {  
        Cleanup(myObj);  
        myObj = null;  
    }  
}  
```  
  
 <span data-ttu-id="86803-108">때문에이 **Dispose** 구현은 동기화 되지 않은, 있기 `Cleanup` 첫 번째 스레드 및 하기 전에 두 번째 스레드가 호출 될 `_myObj` 로 설정 되어 **null**합니다.</span><span class="sxs-lookup"><span data-stu-id="86803-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="86803-109">이 보안 문제 인지에 따라 달라 집니다 때는 `Cleanup` 코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="86803-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="86803-110">동기화 되지 않은 사용 하 여 중요 한 문제가 **Dispose** 구현 파일과 같은 리소스 핸들의 사용이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86803-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="86803-111">메서드를 잘못 사용 될 보안 문제를 일으키는 핸들을 잘못 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86803-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="86803-112">생성자에서 경합 상태</span><span class="sxs-lookup"><span data-stu-id="86803-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="86803-113">일부 응용 프로그램에서는 다른 스레드가 해당 클래스 생성자가 완전히 실행 하려면 먼저 클래스 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86803-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="86803-114">이 발생 하거나 필요한 경우에 스레드를 동기화 해야 하는 경우 보안 문제가 발생 하지는 되도록 모든 클래스 생성자를 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86803-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="86803-115">캐시 된 개체를 사용 하 여 경합</span><span class="sxs-lookup"><span data-stu-id="86803-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="86803-116">보안 정보를 캐시 하거나 코드 액세스 보안을 사용 하는 코드 [Assert](../../../docs/framework/misc/using-the-assert-method.md) 작업 노출 될 수 있습니다 경합 클래스의 다른 부분을 적절 하 게 동기화 되지 않은 경우 다음 예와에서 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="86803-116">Code that caches security information or uses the code access security [Assert](../../../docs/framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
```vb  
Sub SomeSecureFunction()  
    If SomeDemandPasses() Then  
        fCallersOk = True  
        DoOtherWork()  
        fCallersOk = False  
    End If  
End Sub  
  
Sub DoOtherWork()  
    If fCallersOK Then  
        DoSomethingTrusted()  
    Else  
        DemandSomething()  
        DoSomethingTrusted()  
    End If  
End Sub  
```  
  
```csharp  
void SomeSecureFunction()   
{  
    if (SomeDemandPasses())   
    {  
        fCallersOk = true;  
        DoOtherWork();  
        fCallersOk = false;  
    }  
}  
void DoOtherWork()   
{  
    if (fCallersOK)   
    {  
        DoSomethingTrusted();  
    }  
    else   
    {  
        DemandSomething();  
        DoSomethingTrusted();  
    }  
}  
```  
  
 <span data-ttu-id="86803-117">다른 경로가 없으면 `DoOtherWork` 동일한 개체를 사용 하 여 다른 스레드에서 호출 될 수 있는, 신뢰할 수 없는 호출자를 빠져나갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86803-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="86803-118">코드 보안 정보를 캐시 하는 경우이 취약성에 대 한 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86803-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="86803-119">종료자에서 경합 상태</span><span class="sxs-lookup"><span data-stu-id="86803-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="86803-120">해당 종료자에서 해제 되는 정적 또는 관리 되지 않는 리소스를 참조 하는 개체에 경합 상태가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86803-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="86803-121">여러 개체 클래스의 종료자에서 조작 되는 리소스를 공유 하는 경우 개체는 해당 리소스에 대 한 모든 액세스를 동기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86803-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86803-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="86803-122">See also</span></span>

- [<span data-ttu-id="86803-123">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="86803-123">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
