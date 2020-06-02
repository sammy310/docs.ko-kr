---
title: 보안 및 경합 상태
'description:': Describes pitfalls to avoid around security holes exploited by race conditions, including dispose methods, constructors, cached objects, and finalizers.
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
ms.openlocfilehash: 715bf240a5f7f44ba3f914ad6788631074aa41b2
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291021"
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="f4f3a-102">보안 및 경합 상태</span><span class="sxs-lookup"><span data-stu-id="f4f3a-102">Security and Race Conditions</span></span>
<span data-ttu-id="f4f3a-103">또 다른 문제는 경합 상태에서 악용 되는 보안 허점을 일으킬 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="f4f3a-104">이는 여러 가지 방법으로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="f4f3a-105">다음 하위 항목은 개발자가 피해 야 하는 주요 문제 중 일부를 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="f4f3a-106">Dispose 메서드의 경합 상태</span><span class="sxs-lookup"><span data-stu-id="f4f3a-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="f4f3a-107">클래스의 **dispose** 메서드 (자세한 내용은 [가비지 컬렉션](../garbage-collection/index.md)참조)가 동기화 되지 않은 경우 다음 예제와 같이 **dispose** 내의 정리 코드를 두 번 이상 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="f4f3a-108">이 **Dispose** 구현은 동기화 되지 않기 때문에 `Cleanup` 첫 번째 스레드에서를 호출한 다음 `_myObj` 가 **null**로 설정 되기 전에 두 번째 스레드가 호출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="f4f3a-109">보안상 문제가 되는지 여부는 코드가 실행 될 때 발생 하는 상황에 따라 달라 집니다 `Cleanup` .</span><span class="sxs-lookup"><span data-stu-id="f4f3a-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="f4f3a-110">동기화 되지 않은 **Dispose** 구현과 관련 된 주요 문제는 파일 등의 리소스 핸들을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="f4f3a-111">잘못 된 삭제로 인해 잘못 된 핸들이 사용 될 수 있으며,이로 인해 보안 취약성이 발생 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="f4f3a-112">생성자의 경합 상태</span><span class="sxs-lookup"><span data-stu-id="f4f3a-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="f4f3a-113">일부 응용 프로그램에서는 클래스 생성자가 완전히 실행 되기 전에 다른 스레드가 클래스 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="f4f3a-114">모든 클래스 생성자를 검토 하 여이 문제가 발생 하는 경우 보안 문제가 없는지 확인 하거나 필요한 경우 스레드를 동기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="f4f3a-115">캐시 된 개체를 사용 하는 경합 상태</span><span class="sxs-lookup"><span data-stu-id="f4f3a-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="f4f3a-116">보안 정보를 캐시 하거나 코드 액세스 보안 [어설션](../../framework/misc/using-the-assert-method.md) 작업을 사용 하는 코드는 다음 예제와 같이 클래스의 다른 부분이 적절 하 게 동기화 되지 않은 경우 경합 상태에 취약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-116">Code that caches security information or uses the code access security [Assert](../../framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="f4f3a-117">같은 개체를 사용 하는 `DoOtherWork` 다른 스레드에서 호출할 수 있는 다른 경로가 있는 경우 신뢰할 수 없는 호출자가 요청을 지난 후 지연 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="f4f3a-118">코드가 보안 정보를 캐시 하는 경우이 취약점을 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="f4f3a-119">종료자의 경합 상태</span><span class="sxs-lookup"><span data-stu-id="f4f3a-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="f4f3a-120">경합 상태는 해당 종료자에서 해제할 정적 또는 관리 되지 않는 리소스를 참조 하는 개체 에서도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="f4f3a-121">여러 개체가 클래스의 종료자에서 조작 되는 리소스를 공유 하는 경우 개체는 해당 리소스에 대 한 모든 액세스를 동기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4f3a-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4f3a-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4f3a-122">See also</span></span>

- [<span data-ttu-id="f4f3a-123">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="f4f3a-123">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)
