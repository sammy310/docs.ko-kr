---
description: '자세한 정보: BC31535: Friend 어셈블리 참조가 잘못 되었습니다. <reference>'
title: Friend 어셈블리 참조 <reference>이(가) 잘못되었습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: e3e08edede9bee4710c415a61592857229ea4f35
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796199"
---
# <a name="bc31535-friend-assembly-reference-reference-is-invalid"></a>BC31535: Friend 어셈블리 참조가 \<reference> 잘못 되었습니다.

Friend 어셈블리 참조가 \<reference> 잘못 되었습니다. 강력한 이름의 서명된 어셈블리는 InternalsVisibleTo 선언에 공개 키를 지정해야 합니다.

 특성 생성자에 전달 된 어셈블리 이름은 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 강력한 이름의 어셈블리를 식별 하지만 특성은 포함 하지 않습니다 `PublicKey` .

 **오류 ID:** BC31535

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. 강력한 이름의 friend 어셈블리에 대 한 공개 키를 확인 합니다. <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>특성을 사용 하 여 특성 생성자에 전달 된 어셈블리 이름의 일부로 공개 키를 포함 `PublicKey` 합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Reflection.AssemblyName>
- [Friend 어셈블리](../../../standard/assembly/friend.md)
