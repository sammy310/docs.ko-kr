---
title: 선언 컨텍스트 및 기본 액세스 수준
ms.date: 07/20/2015
helpviewer_keywords:
- module level, defined
- declaration contexts, Visual Basic
- procedure level, defined
- namespace level, defined
- access levels, Visual Basic
- access levels, default levels
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
ms.openlocfilehash: 1ba25d830b1e7529bdf09c1195cc1fe7f9b2243b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354097"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>선언 컨텍스트 및 기본 액세스 수준(Visual Basic)
This topic describes which Visual Basic types can be declared within which other types, and what their access levels default to if not specified.  
  
## <a name="declaration-context-levels"></a>Declaration Context Levels  
 The *declaration context* of a programming element is the region of code in which it is declared. This is often another programming element, which is then called the *containing element*.  
  
 The levels for declaration contexts are the following:  
  
- *Namespace level* — within a source file or namespace but not within a class, structure, module, or interface  
  
- *Module level* — within a class, structure, module, or interface but not within a procedure or block  
  
- *Procedure level* — within a procedure or block (such as `If` or `For`)  
  
 The following table shows the default access levels for various declared programming elements, depending on their declaration contexts.  
  
|선언 요소|Namespace level|Module level|Procedure level|  
|----------------------|---------------------|------------------|---------------------|  
|Variable ([Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md))|허용되지 않음|`Private` (`Public` in `Structure`, not allowed in `Interface`)|`Public`|  
|Constant ([Const Statement](../../../visual-basic/language-reference/statements/const-statement.md))|허용되지 않음|`Private` (`Public` in `Structure`, not allowed in `Interface`)|`Public`|  
|Enumeration ([Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md))|`Friend`|`Public`|허용되지 않음|  
|Class ([Class Statement](../../../visual-basic/language-reference/statements/class-statement.md))|`Friend`|`Public`|허용되지 않음|  
|Structure ([Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md))|`Friend`|`Public`|허용되지 않음|  
|Module ([Module Statement](../../../visual-basic/language-reference/statements/module-statement.md))|`Friend`|허용되지 않음|허용되지 않음|  
|Interface ([Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md))|`Friend`|`Public`|허용되지 않음|  
|Procedure ([Function Statement](../../../visual-basic/language-reference/statements/function-statement.md), [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md))|허용되지 않음|`Public`|허용되지 않음|  
|External reference ([Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md))|허용되지 않음|`Public` (not allowed in `Interface`)|허용되지 않음|  
|Operator ([Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md))|허용되지 않음|`Public` (not allowed in `Interface` or `Module`)|허용되지 않음|  
|Property ([Property Statement](../../../visual-basic/language-reference/statements/property-statement.md))|허용되지 않음|`Public`|허용되지 않음|  
|Default property ([Default](../../../visual-basic/language-reference/modifiers/default.md))|허용되지 않음|`Public` (not allowed in `Module`)|허용되지 않음|  
|Event ([Event Statement](../../../visual-basic/language-reference/statements/event-statement.md))|허용되지 않음|`Public`|허용되지 않음|  
|Delegate ([Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md))|`Friend`|`Public`|허용되지 않음|  
  
 For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>참조

- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [전용](../../../visual-basic/language-reference/modifiers/private.md)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
