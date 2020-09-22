---
title: SyncLock 문
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: cc8706b95e0785459e36abe27ce915b5bab8711a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875197"
---
# <a name="synclock-statement"></a>SyncLock 문

블록을 실행 하기 전에 문 블록에 대 한 단독 잠금을 획득 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a>부분  

 `lockobject`  
 필수 사항입니다. 개체 참조로 계산 되는 식입니다.  
  
 `block`  
 선택 사항입니다. 잠금을 획득할 때 실행할 문 블록입니다.  
  
 `End SyncLock`  
 블록을 종료 `SyncLock` 합니다.  
  
## <a name="remarks"></a>설명  

 문을 사용 하면 `SyncLock` 여러 스레드가 동시에 문 블록을 실행 하지 않습니다. `SyncLock` 다른 스레드가 실행 하지 않을 때까지 각 스레드가 블록을 입력 하지 않도록 합니다.  
  
 의 가장 일반적인 용도는 `SyncLock` 두 개 이상의 스레드에서 데이터를 동시에 업데이트 하지 않도록 보호 하는 것입니다. 데이터를 조작 하는 문이 중단 없이 완료로 이동 해야 하는 경우 블록 안에 배치 합니다 `SyncLock` .  
  
 배타적 잠금으로 보호 되는 문 블록은 *임계 영역*이 라고도 합니다.  
  
## <a name="rules"></a>규칙  
  
- 분기. 블록 외부에서 블록으로 분기할 수 없습니다 `SyncLock` .  
  
- 잠금 개체 값입니다. 값은 `lockobject` 일 수 없습니다 `Nothing` . 문에서 사용 하기 전에 lock 개체를 만들어야 합니다 `SyncLock` .  
  
     `lockobject`블록을 실행 하는 동안의 값은 변경할 수 없습니다 `SyncLock` . 이 메커니즘을 사용 하려면 lock 개체가 변경 되지 않은 상태로 유지 되어야 합니다.  
  
- 블록에는 [wait](../operators/await-operator.md) 연산자를 사용할 수 없습니다 `SyncLock` .  
  
## <a name="behavior"></a>동작  
  
- 방법일. 스레드가 문에 도달 하면 `SyncLock` 식을 계산 하 `lockobject` 고 식에서 반환 되는 개체에 대 한 배타적 잠금을 획득할 때까지 실행을 일시 중단 합니다. 다른 스레드가 문에 도달 하면 `SyncLock` 첫 번째 스레드가 문을 실행할 때까지 잠금을 획득 하지 않습니다 `End SyncLock` .  
  
- 보호 된 데이터입니다. `lockobject`가 변수인 경우 `Shared` 단독 잠금은 클래스의 모든 인스턴스에서 스레드가 실행 되는 동안 블록을 실행 하는 것을 방지 합니다 `SyncLock` . 이는 모든 인스턴스 간에 공유 되는 데이터를 보호 합니다.  
  
     `lockobject`가이 아닌 인스턴스 변수인 경우 `Shared` 잠금은 현재 인스턴스에서 실행 되는 스레드가 `SyncLock` 같은 인스턴스의 다른 스레드와 동시에 블록을 실행 하지 않도록 합니다. 그러면 개별 인스턴스에 의해 유지 관리 되는 데이터가 보호 됩니다.  
  
- 취득 및 릴리스. 블록은 `SyncLock` `Try...Finally` `Try` 블록이에서 배타적 잠금을 획득 하 고 블록에서 해제 하는 생성 처럼 동작 `lockobject` `Finally` 합니다. 따라서 블록을 `SyncLock` 종료 하는 방법에 관계 없이 블록은 잠금 해제를 보장 합니다. 처리 되지 않은 예외의 경우에도 마찬가지입니다.  
  
- 프레임 워크 호출. `SyncLock`블록은 `Enter` `Exit` `Monitor` 네임 스페이스에서 클래스의 및 메서드를 호출 하 여 단독 잠금을 획득 하 고 해제 합니다 <xref:System.Threading> .  
  
## <a name="programming-practices"></a>프로그래밍 방법  

 `lockobject`식은 항상 클래스에 독점적으로 속하는 개체로 계산 되어야 합니다. `Private`현재 인스턴스에 속하는 데이터를 보호 하기 위해 개체 변수를 선언 하거나 개체 변수를 선언 하 여 `Private Shared` 모든 인스턴스에 공통적인 데이터를 보호 해야 합니다.  
  
 키워드를 사용 하 여 `Me` 인스턴스 데이터에 대 한 잠금 개체를 제공 하면 안 됩니다. 클래스 외부의 코드에 클래스의 인스턴스에 대 한 참조가 있는 경우 해당 참조를 `SyncLock` 다른 데이터를 보호 하는 것과 완전히 다른 블록에 대 한 잠금 개체로 사용할 수 있습니다. 이러한 방식으로 클래스와 다른 클래스는 관련 되지 않은 블록을 실행 하지 못하도록 차단할 수 있습니다 `SyncLock` . 동일한 문자열을 사용 하는 프로세스의 다른 코드가 동일한 잠금을 공유 하기 때문에 문자열에 대 한 잠금과 잠금은 문제가 될 수 있습니다.  
  
 또한 메서드를 사용 하 여 `Me.GetType` 공유 데이터에 대 한 잠금 개체를 제공 해서는 안 됩니다. 이는 `GetType` 항상 `Type` 지정 된 클래스 이름에 대해 같은 개체를 반환 하기 때문입니다. 외부 코드는 `GetType` 클래스에 대해를 호출 하 고 사용 하는 것과 동일한 잠금 개체를 가져올 수 있습니다. 이로 인해 두 클래스가 해당 블록에서 서로 차단 `SyncLock` 됩니다.  
  
## <a name="examples"></a>예  
  
### <a name="description"></a>Description  

 다음 예제에서는 간단한 메시지 목록을 유지 관리 하는 클래스를 보여 줍니다. 배열에 있는 메시지와 해당 배열의 마지막으로 사용 된 요소를 변수에 저장 합니다. 이 `addAnotherMessage` 프로시저는 마지막 요소를 증가 시키고 새 메시지를 저장 합니다. 이러한 두 작업은 `SyncLock` 및 문으로 보호 됩니다 `End SyncLock` . 마지막 요소를 증가 시킨 후에는 새 메시지를 저장 해야 다른 스레드가 마지막 요소를 다시 증가 시킬 수 있습니다.  
  
 `simpleMessageList`클래스가 모든 인스턴스 간에 메시지 목록 하나를 공유 하는 경우 및 변수는 `messagesList` `messagesLast` 로 선언 됩니다 `Shared` . 이 경우 변수는 `messagesLock` 여야 `Shared` 하므로 모든 인스턴스에서 단일 잠금 개체가 사용 됩니다.  
  
### <a name="code"></a>코드  

 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a>Description  

 다음 예제에서는 및 스레드를 사용 `SyncLock` 합니다. `SyncLock`문이 있으면 문 블록은 임계 섹션이 되며 `balance` 음수가 될 수 없습니다. 및 문을 주석으로 처리 하 여 키워드를 종료 하는 효과를 확인할 수 있습니다 `SyncLock` `End SyncLock` `SyncLock` .  
  
### <a name="code"></a>코드  

 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a>주석  
  
## <a name="see-also"></a>참조

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [동기화 기본 형식 개요](../../../standard/threading/overview-of-synchronization-primitives.md)
