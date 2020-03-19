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
ms.openlocfilehash: 09d8d0d6e85af04fe0fb00f53df408126012081e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186788"
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="46ab3-102">보안 및 경합 상태</span><span class="sxs-lookup"><span data-stu-id="46ab3-102">Security and Race Conditions</span></span>
<span data-ttu-id="46ab3-103">또 다른 우려 영역은 경주 조건에 의해 악용되는 보안 허점의 가능성입니다.</span><span class="sxs-lookup"><span data-stu-id="46ab3-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="46ab3-104">이 문제가 발생할 수 있는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ab3-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="46ab3-105">다음 하위 항목은 개발자가 피해야 하는 몇 가지 주요 함정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="46ab3-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="46ab3-106">처분 방식의 레이스 조건</span><span class="sxs-lookup"><span data-stu-id="46ab3-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="46ab3-107">클래스의 **Dispose** 메서드(자세한 내용은 [가비지 수집](../../../docs/standard/garbage-collection/index.md)참조)가 동기화되지 않은 경우 다음 예제와 같이 **Dispose** 내부의 정리 코드를 두 번 이상 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ab3-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="46ab3-108">이 **Dispose** 구현은 동기화되지 않으므로 첫 `Cleanup` 번째 스레드에서 호출한 다음 두 번째 `_myObj` 스레드를 **null로**설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ab3-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="46ab3-109">이것이 보안 문제인지 여부는 `Cleanup` 코드가 실행될 때 발생하는 상황에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="46ab3-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="46ab3-110">동기화되지 않은 **Dispose** 구현의 주요 문제는 파일과 같은 리소스 핸들을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="46ab3-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="46ab3-111">부적절한 처리로 인해 잘못된 핸들이 사용될 수 있으며, 이로 인해 보안 취약점이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ab3-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="46ab3-112">생성자 내의 레이스 조건</span><span class="sxs-lookup"><span data-stu-id="46ab3-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="46ab3-113">일부 응용 프로그램에서는 클래스 생성자가 완전히 실행되기 전에 다른 스레드가 클래스 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ab3-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="46ab3-114">모든 클래스 생성자검토하여 이 문제가 발생할 경우 보안 문제가 없는지 확인하거나 필요한 경우 스레드를 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46ab3-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="46ab3-115">캐시된 객체가 있는 경합 조건</span><span class="sxs-lookup"><span data-stu-id="46ab3-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="46ab3-116">다음 예제와 같이 보안 정보를 캐시하거나 코드 액세스 보안 [Assert](../../../docs/framework/misc/using-the-assert-method.md) 작업을 사용하는 코드는 클래스의 다른 부분이 적절하게 동기화되지 않은 경우 경합 조건에 취약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ab3-116">Code that caches security information or uses the code access security [Assert](../../../docs/framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="46ab3-117">동일한 개체를 `DoOtherWork` 가진 다른 스레드에서 호출할 수 있는 다른 경로가 있는 경우 신뢰할 수 없는 호출자는 요청을 통과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ab3-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="46ab3-118">코드가 보안 정보를 캐시하는 경우 이 취약점을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46ab3-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="46ab3-119">종료자의 레이스 조건</span><span class="sxs-lookup"><span data-stu-id="46ab3-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="46ab3-120">경합 조건은 정적 또는 관리되지 않는 리소스를 참조한 다음 종료자에서 해제하는 개체에서도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46ab3-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="46ab3-121">여러 개체가 클래스의 종료자에서 조작된 리소스를 공유하는 경우 개체는 해당 리소스에 대한 모든 액세스를 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46ab3-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46ab3-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46ab3-122">See also</span></span>

- [<span data-ttu-id="46ab3-123">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="46ab3-123">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
