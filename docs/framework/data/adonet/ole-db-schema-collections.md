---
title: OLE DB 스키마 컬렉션
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 2d5718c12100ebea49a6b6fab29a3790918c6ad3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783455"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="89f14-102">OLE DB 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="89f14-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="89f14-103">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 OLE DB 공급자에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="89f14-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="89f14-104">Microsoft SQL Server OLE DB 공급자</span><span class="sxs-lookup"><span data-stu-id="89f14-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="89f14-105">Microsoft SQL Server OLE DB 드라이버는 공통 스키마 컬렉션 외에도 다음과 같은 특정 스키마 컬렉션을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="89f14-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="89f14-106">테이블</span><span class="sxs-lookup"><span data-stu-id="89f14-106">Tables</span></span>  
  
- <span data-ttu-id="89f14-107">열</span><span class="sxs-lookup"><span data-stu-id="89f14-107">Columns</span></span>  
  
- <span data-ttu-id="89f14-108">절차</span><span class="sxs-lookup"><span data-stu-id="89f14-108">Procedures</span></span>  
  
- <span data-ttu-id="89f14-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="89f14-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="89f14-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="89f14-110">Catalog</span></span>  
  
- <span data-ttu-id="89f14-111">인덱스</span><span class="sxs-lookup"><span data-stu-id="89f14-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="89f14-112">테이블</span><span class="sxs-lookup"><span data-stu-id="89f14-112">Tables</span></span>  
  
|<span data-ttu-id="89f14-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="89f14-113">ColumnName</span></span>|<span data-ttu-id="89f14-114">DataType</span><span class="sxs-lookup"><span data-stu-id="89f14-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="89f14-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-115">TABLE_CATALOG</span></span>|<span data-ttu-id="89f14-116">String</span><span class="sxs-lookup"><span data-stu-id="89f14-116">String</span></span>|  
|<span data-ttu-id="89f14-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="89f14-118">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-118">String</span></span>|  
|<span data-ttu-id="89f14-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-119">TABLE_NAME</span></span>|<span data-ttu-id="89f14-120">String</span><span class="sxs-lookup"><span data-stu-id="89f14-120">String</span></span>|  
|<span data-ttu-id="89f14-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="89f14-121">TABLE_TYPE</span></span>|<span data-ttu-id="89f14-122">String</span><span class="sxs-lookup"><span data-stu-id="89f14-122">String</span></span>|  
|<span data-ttu-id="89f14-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="89f14-123">TABLE_GUID</span></span>|<span data-ttu-id="89f14-124">Guid</span><span class="sxs-lookup"><span data-stu-id="89f14-124">Guid</span></span>|  
|<span data-ttu-id="89f14-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89f14-125">DESCRIPTION</span></span>|<span data-ttu-id="89f14-126">String</span><span class="sxs-lookup"><span data-stu-id="89f14-126">String</span></span>|  
|<span data-ttu-id="89f14-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="89f14-127">TABLE_PROPID</span></span>|<span data-ttu-id="89f14-128">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-128">Int64</span></span>|  
|<span data-ttu-id="89f14-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="89f14-129">DATE_CREATED</span></span>|<span data-ttu-id="89f14-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="89f14-130">DateTime</span></span>|  
|<span data-ttu-id="89f14-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="89f14-131">DATE_MODIFIED</span></span>|<span data-ttu-id="89f14-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="89f14-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="89f14-133">열</span><span class="sxs-lookup"><span data-stu-id="89f14-133">Columns</span></span>  
  
|<span data-ttu-id="89f14-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="89f14-134">ColumnName</span></span>|<span data-ttu-id="89f14-135">DataType</span><span class="sxs-lookup"><span data-stu-id="89f14-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="89f14-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-136">TABLE_CATALOG</span></span>|<span data-ttu-id="89f14-137">String</span><span class="sxs-lookup"><span data-stu-id="89f14-137">String</span></span>|  
|<span data-ttu-id="89f14-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="89f14-139">String</span><span class="sxs-lookup"><span data-stu-id="89f14-139">String</span></span>|  
|<span data-ttu-id="89f14-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-140">TABLE_NAME</span></span>|<span data-ttu-id="89f14-141">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-141">String</span></span>|  
|<span data-ttu-id="89f14-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-142">COLUMN_NAME</span></span>|<span data-ttu-id="89f14-143">String</span><span class="sxs-lookup"><span data-stu-id="89f14-143">String</span></span>|  
|<span data-ttu-id="89f14-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="89f14-144">COLUMN_GUID</span></span>|<span data-ttu-id="89f14-145">Guid</span><span class="sxs-lookup"><span data-stu-id="89f14-145">Guid</span></span>|  
|<span data-ttu-id="89f14-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="89f14-146">COLUMN_PROPID</span></span>|<span data-ttu-id="89f14-147">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-147">Int64</span></span>|  
|<span data-ttu-id="89f14-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="89f14-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="89f14-149">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-149">Int64</span></span>|  
|<span data-ttu-id="89f14-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="89f14-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="89f14-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-151">Boolean</span></span>|  
|<span data-ttu-id="89f14-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="89f14-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="89f14-153">String</span><span class="sxs-lookup"><span data-stu-id="89f14-153">String</span></span>|  
|<span data-ttu-id="89f14-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="89f14-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="89f14-155">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-155">Int64</span></span>|  
|<span data-ttu-id="89f14-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="89f14-156">IS_NULLABLE</span></span>|<span data-ttu-id="89f14-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-157">Boolean</span></span>|  
|<span data-ttu-id="89f14-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="89f14-158">DATA_TYPE</span></span>|<span data-ttu-id="89f14-159">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-159">Int32</span></span>|  
|<span data-ttu-id="89f14-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="89f14-160">TYPE_GUID</span></span>|<span data-ttu-id="89f14-161">Guid</span><span class="sxs-lookup"><span data-stu-id="89f14-161">Guid</span></span>|  
|<span data-ttu-id="89f14-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="89f14-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="89f14-163">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-163">Int64</span></span>|  
|<span data-ttu-id="89f14-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="89f14-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="89f14-165">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-165">Int64</span></span>|  
|<span data-ttu-id="89f14-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="89f14-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="89f14-167">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-167">Int32</span></span>|  
|<span data-ttu-id="89f14-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="89f14-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="89f14-169">Int16</span><span class="sxs-lookup"><span data-stu-id="89f14-169">Int16</span></span>|  
|<span data-ttu-id="89f14-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="89f14-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="89f14-171">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-171">Int64</span></span>|  
|<span data-ttu-id="89f14-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="89f14-173">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-173">String</span></span>|  
|<span data-ttu-id="89f14-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="89f14-175">String</span><span class="sxs-lookup"><span data-stu-id="89f14-175">String</span></span>|  
|<span data-ttu-id="89f14-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="89f14-177">String</span><span class="sxs-lookup"><span data-stu-id="89f14-177">String</span></span>|  
|<span data-ttu-id="89f14-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="89f14-179">String</span><span class="sxs-lookup"><span data-stu-id="89f14-179">String</span></span>|  
|<span data-ttu-id="89f14-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="89f14-181">String</span><span class="sxs-lookup"><span data-stu-id="89f14-181">String</span></span>|  
|<span data-ttu-id="89f14-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-182">COLLATION_NAME</span></span>|<span data-ttu-id="89f14-183">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-183">String</span></span>|  
|<span data-ttu-id="89f14-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="89f14-185">String</span><span class="sxs-lookup"><span data-stu-id="89f14-185">String</span></span>|  
|<span data-ttu-id="89f14-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="89f14-187">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-187">String</span></span>|  
|<span data-ttu-id="89f14-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-188">DOMAIN_NAME</span></span>|<span data-ttu-id="89f14-189">String</span><span class="sxs-lookup"><span data-stu-id="89f14-189">String</span></span>|  
|<span data-ttu-id="89f14-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89f14-190">DESCRIPTION</span></span>|<span data-ttu-id="89f14-191">String</span><span class="sxs-lookup"><span data-stu-id="89f14-191">String</span></span>|  
|<span data-ttu-id="89f14-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="89f14-192">COLUMN_LCID</span></span>|<span data-ttu-id="89f14-193">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-193">Int32</span></span>|  
|<span data-ttu-id="89f14-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="89f14-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="89f14-195">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-195">Int32</span></span>|  
|<span data-ttu-id="89f14-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="89f14-196">COLUMN_SORTID</span></span>|<span data-ttu-id="89f14-197">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-197">Int32</span></span>|  
|<span data-ttu-id="89f14-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="89f14-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="89f14-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="89f14-199">Byte[]</span></span>|  
|<span data-ttu-id="89f14-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="89f14-200">IS_COMPUTED</span></span>|<span data-ttu-id="89f14-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="89f14-202">절차</span><span class="sxs-lookup"><span data-stu-id="89f14-202">Procedures</span></span>  
  
|<span data-ttu-id="89f14-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="89f14-203">ColumnName</span></span>|<span data-ttu-id="89f14-204">DataType</span><span class="sxs-lookup"><span data-stu-id="89f14-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="89f14-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="89f14-206">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-206">String</span></span>|  
|<span data-ttu-id="89f14-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="89f14-208">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-208">String</span></span>|  
|<span data-ttu-id="89f14-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="89f14-210">String</span><span class="sxs-lookup"><span data-stu-id="89f14-210">String</span></span>|  
|<span data-ttu-id="89f14-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="89f14-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="89f14-212">Int16</span><span class="sxs-lookup"><span data-stu-id="89f14-212">Int16</span></span>|  
|<span data-ttu-id="89f14-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="89f14-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="89f14-214">String</span><span class="sxs-lookup"><span data-stu-id="89f14-214">String</span></span>|  
|<span data-ttu-id="89f14-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89f14-215">DESCRIPTION</span></span>|<span data-ttu-id="89f14-216">String</span><span class="sxs-lookup"><span data-stu-id="89f14-216">String</span></span>|  
|<span data-ttu-id="89f14-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="89f14-217">DATE_CREATED</span></span>|<span data-ttu-id="89f14-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="89f14-218">DateTime</span></span>|  
|<span data-ttu-id="89f14-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="89f14-219">DATE_MODIFIED</span></span>|<span data-ttu-id="89f14-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="89f14-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="89f14-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="89f14-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="89f14-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="89f14-222">ColumnName</span></span>|<span data-ttu-id="89f14-223">DataType</span><span class="sxs-lookup"><span data-stu-id="89f14-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="89f14-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="89f14-225">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-225">String</span></span>|  
|<span data-ttu-id="89f14-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="89f14-227">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-227">String</span></span>|  
|<span data-ttu-id="89f14-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="89f14-229">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-229">String</span></span>|  
|<span data-ttu-id="89f14-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-230">PARAMETER_NAME</span></span>|<span data-ttu-id="89f14-231">String</span><span class="sxs-lookup"><span data-stu-id="89f14-231">String</span></span>|  
|<span data-ttu-id="89f14-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="89f14-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="89f14-233">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-233">Int32</span></span>|  
|<span data-ttu-id="89f14-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="89f14-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="89f14-235">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-235">Int32</span></span>|  
|<span data-ttu-id="89f14-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="89f14-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="89f14-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-237">Boolean</span></span>|  
|<span data-ttu-id="89f14-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="89f14-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="89f14-239">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-239">String</span></span>|  
|<span data-ttu-id="89f14-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="89f14-240">IS_NULLABLE</span></span>|<span data-ttu-id="89f14-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-241">Boolean</span></span>|  
|<span data-ttu-id="89f14-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="89f14-242">DATA_TYPE</span></span>|<span data-ttu-id="89f14-243">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-243">Int32</span></span>|  
|<span data-ttu-id="89f14-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="89f14-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="89f14-245">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-245">Int64</span></span>|  
|<span data-ttu-id="89f14-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="89f14-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="89f14-247">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-247">Int64</span></span>|  
|<span data-ttu-id="89f14-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="89f14-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="89f14-249">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-249">Int32</span></span>|  
|<span data-ttu-id="89f14-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="89f14-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="89f14-251">Int16</span><span class="sxs-lookup"><span data-stu-id="89f14-251">Int16</span></span>|  
|<span data-ttu-id="89f14-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89f14-252">DESCRIPTION</span></span>|<span data-ttu-id="89f14-253">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-253">String</span></span>|  
|<span data-ttu-id="89f14-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-254">TYPE_NAME</span></span>|<span data-ttu-id="89f14-255">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-255">String</span></span>|  
|<span data-ttu-id="89f14-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="89f14-257">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="89f14-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="89f14-258">Catalog</span></span>  
  
|<span data-ttu-id="89f14-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="89f14-259">ColumnName</span></span>|<span data-ttu-id="89f14-260">DataType</span><span class="sxs-lookup"><span data-stu-id="89f14-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="89f14-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-261">CATALOG_NAME</span></span>|<span data-ttu-id="89f14-262">String</span><span class="sxs-lookup"><span data-stu-id="89f14-262">String</span></span>|  
|<span data-ttu-id="89f14-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89f14-263">DESCRIPTION</span></span>|<span data-ttu-id="89f14-264">String</span><span class="sxs-lookup"><span data-stu-id="89f14-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="89f14-265">인덱스</span><span class="sxs-lookup"><span data-stu-id="89f14-265">Indexes</span></span>  
  
|<span data-ttu-id="89f14-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="89f14-266">ColumnName</span></span>|<span data-ttu-id="89f14-267">DataType</span><span class="sxs-lookup"><span data-stu-id="89f14-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="89f14-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-268">TABLE_CATALOG</span></span>|<span data-ttu-id="89f14-269">String</span><span class="sxs-lookup"><span data-stu-id="89f14-269">String</span></span>|  
|<span data-ttu-id="89f14-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="89f14-271">String</span><span class="sxs-lookup"><span data-stu-id="89f14-271">String</span></span>|  
|<span data-ttu-id="89f14-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-272">TABLE_NAME</span></span>|<span data-ttu-id="89f14-273">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-273">String</span></span>|  
|<span data-ttu-id="89f14-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-274">INDEX_CATALOG</span></span>|<span data-ttu-id="89f14-275">String</span><span class="sxs-lookup"><span data-stu-id="89f14-275">String</span></span>|  
|<span data-ttu-id="89f14-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="89f14-277">String</span><span class="sxs-lookup"><span data-stu-id="89f14-277">String</span></span>|  
|<span data-ttu-id="89f14-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-278">INDEX_NAME</span></span>|<span data-ttu-id="89f14-279">String</span><span class="sxs-lookup"><span data-stu-id="89f14-279">String</span></span>|  
|<span data-ttu-id="89f14-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="89f14-280">PRIMARY_KEY</span></span>|<span data-ttu-id="89f14-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-281">Boolean</span></span>|  
|<span data-ttu-id="89f14-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="89f14-282">UNIQUE</span></span>|<span data-ttu-id="89f14-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-283">Boolean</span></span>|  
|<span data-ttu-id="89f14-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="89f14-284">CLUSTERED</span></span>|<span data-ttu-id="89f14-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-285">Boolean</span></span>|  
|<span data-ttu-id="89f14-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="89f14-286">TYPE</span></span>|<span data-ttu-id="89f14-287">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-287">Int32</span></span>|  
|<span data-ttu-id="89f14-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="89f14-288">FILL_FACTOR</span></span>|<span data-ttu-id="89f14-289">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-289">Int32</span></span>|  
|<span data-ttu-id="89f14-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="89f14-290">INITIAL_SIZE</span></span>|<span data-ttu-id="89f14-291">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-291">Int32</span></span>|  
|<span data-ttu-id="89f14-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="89f14-292">NULLS</span></span>|<span data-ttu-id="89f14-293">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-293">Int32</span></span>|  
|<span data-ttu-id="89f14-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="89f14-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="89f14-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-295">Boolean</span></span>|  
|<span data-ttu-id="89f14-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="89f14-296">AUTO_UPDATE</span></span>|<span data-ttu-id="89f14-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-297">Boolean</span></span>|  
|<span data-ttu-id="89f14-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="89f14-298">NULL_COLLATION</span></span>|<span data-ttu-id="89f14-299">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-299">Int32</span></span>|  
|<span data-ttu-id="89f14-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="89f14-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="89f14-301">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-301">Int64</span></span>|  
|<span data-ttu-id="89f14-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-302">COLUMN_NAME</span></span>|<span data-ttu-id="89f14-303">String</span><span class="sxs-lookup"><span data-stu-id="89f14-303">String</span></span>|  
|<span data-ttu-id="89f14-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="89f14-304">COLUMN_GUID</span></span>|<span data-ttu-id="89f14-305">Guid</span><span class="sxs-lookup"><span data-stu-id="89f14-305">Guid</span></span>|  
|<span data-ttu-id="89f14-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="89f14-306">COLUMN_PROPID</span></span>|<span data-ttu-id="89f14-307">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-307">Int64</span></span>|  
|<span data-ttu-id="89f14-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="89f14-308">COLLATION</span></span>|<span data-ttu-id="89f14-309">Int16</span><span class="sxs-lookup"><span data-stu-id="89f14-309">Int16</span></span>|  
|<span data-ttu-id="89f14-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="89f14-310">CARDINALITY</span></span>|<span data-ttu-id="89f14-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="89f14-311">Decimal</span></span>|  
|<span data-ttu-id="89f14-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="89f14-312">PAGES</span></span>|<span data-ttu-id="89f14-313">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-313">Int32</span></span>|  
|<span data-ttu-id="89f14-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="89f14-314">FILTER_CONDITION</span></span>|<span data-ttu-id="89f14-315">String</span><span class="sxs-lookup"><span data-stu-id="89f14-315">String</span></span>|  
|<span data-ttu-id="89f14-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="89f14-316">INTEGRATED</span></span>|<span data-ttu-id="89f14-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="89f14-318">Microsoft Oracle OLE DB</span><span class="sxs-lookup"><span data-stu-id="89f14-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="89f14-319">Microsoft Oracle OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="89f14-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="89f14-320">테이블</span><span class="sxs-lookup"><span data-stu-id="89f14-320">Tables</span></span>  
  
- <span data-ttu-id="89f14-321">열</span><span class="sxs-lookup"><span data-stu-id="89f14-321">Columns</span></span>  
  
- <span data-ttu-id="89f14-322">절차</span><span class="sxs-lookup"><span data-stu-id="89f14-322">Procedures</span></span>  
  
- <span data-ttu-id="89f14-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="89f14-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="89f14-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="89f14-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="89f14-325">뷰</span><span class="sxs-lookup"><span data-stu-id="89f14-325">Views</span></span>  
  
- <span data-ttu-id="89f14-326">인덱스</span><span class="sxs-lookup"><span data-stu-id="89f14-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="89f14-327">테이블</span><span class="sxs-lookup"><span data-stu-id="89f14-327">Tables</span></span>  
  
|<span data-ttu-id="89f14-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="89f14-328">ColumnName</span></span>|<span data-ttu-id="89f14-329">DataType</span><span class="sxs-lookup"><span data-stu-id="89f14-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="89f14-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-330">TABLE_CATALOG</span></span>|<span data-ttu-id="89f14-331">String</span><span class="sxs-lookup"><span data-stu-id="89f14-331">String</span></span>|  
|<span data-ttu-id="89f14-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="89f14-333">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-333">String</span></span>|  
|<span data-ttu-id="89f14-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-334">TABLE_NAME</span></span>|<span data-ttu-id="89f14-335">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-335">String</span></span>|  
|<span data-ttu-id="89f14-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="89f14-336">TABLE_TYPE</span></span>|<span data-ttu-id="89f14-337">String</span><span class="sxs-lookup"><span data-stu-id="89f14-337">String</span></span>|  
|<span data-ttu-id="89f14-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="89f14-338">TABLE_GUID</span></span>|<span data-ttu-id="89f14-339">Guid</span><span class="sxs-lookup"><span data-stu-id="89f14-339">Guid</span></span>|  
|<span data-ttu-id="89f14-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89f14-340">DESCRIPTION</span></span>|<span data-ttu-id="89f14-341">String</span><span class="sxs-lookup"><span data-stu-id="89f14-341">String</span></span>|  
|<span data-ttu-id="89f14-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="89f14-342">TABLE_PROPID</span></span>|<span data-ttu-id="89f14-343">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-343">Int64</span></span>|  
|<span data-ttu-id="89f14-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="89f14-344">DATE_CREATED</span></span>|<span data-ttu-id="89f14-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="89f14-345">DateTime</span></span>|  
|<span data-ttu-id="89f14-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="89f14-346">DATE_MODIFIED</span></span>|<span data-ttu-id="89f14-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="89f14-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="89f14-348">열</span><span class="sxs-lookup"><span data-stu-id="89f14-348">Columns</span></span>  
  
|<span data-ttu-id="89f14-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="89f14-349">ColumnName</span></span>|<span data-ttu-id="89f14-350">DataType</span><span class="sxs-lookup"><span data-stu-id="89f14-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="89f14-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-351">TABLE_CATALOG</span></span>|<span data-ttu-id="89f14-352">String</span><span class="sxs-lookup"><span data-stu-id="89f14-352">String</span></span>|  
|<span data-ttu-id="89f14-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="89f14-354">String</span><span class="sxs-lookup"><span data-stu-id="89f14-354">String</span></span>|  
|<span data-ttu-id="89f14-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-355">TABLE_NAME</span></span>|<span data-ttu-id="89f14-356">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-356">String</span></span>|  
|<span data-ttu-id="89f14-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-357">COLUMN_NAME</span></span>|<span data-ttu-id="89f14-358">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-358">String</span></span>|  
|<span data-ttu-id="89f14-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="89f14-359">COLUMN_GUID</span></span>|<span data-ttu-id="89f14-360">Guid</span><span class="sxs-lookup"><span data-stu-id="89f14-360">Guid</span></span>|  
|<span data-ttu-id="89f14-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="89f14-361">COLUMN_PROPID</span></span>|<span data-ttu-id="89f14-362">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-362">Int64</span></span>|  
|<span data-ttu-id="89f14-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="89f14-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="89f14-364">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-364">Int64</span></span>|  
|<span data-ttu-id="89f14-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="89f14-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="89f14-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-366">Boolean</span></span>|  
|<span data-ttu-id="89f14-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="89f14-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="89f14-368">String</span><span class="sxs-lookup"><span data-stu-id="89f14-368">String</span></span>|  
|<span data-ttu-id="89f14-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="89f14-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="89f14-370">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-370">Int64</span></span>|  
|<span data-ttu-id="89f14-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="89f14-371">IS_NULLABLE</span></span>|<span data-ttu-id="89f14-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-372">Boolean</span></span>|  
|<span data-ttu-id="89f14-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="89f14-373">DATA_TYPE</span></span>|<span data-ttu-id="89f14-374">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-374">Int32</span></span>|  
|<span data-ttu-id="89f14-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="89f14-375">TYPE_GUID</span></span>|<span data-ttu-id="89f14-376">Guid</span><span class="sxs-lookup"><span data-stu-id="89f14-376">Guid</span></span>|  
|<span data-ttu-id="89f14-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="89f14-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="89f14-378">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-378">Int64</span></span>|  
|<span data-ttu-id="89f14-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="89f14-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="89f14-380">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-380">Int64</span></span>|  
|<span data-ttu-id="89f14-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="89f14-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="89f14-382">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-382">Int32</span></span>|  
|<span data-ttu-id="89f14-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="89f14-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="89f14-384">Int16</span><span class="sxs-lookup"><span data-stu-id="89f14-384">Int16</span></span>|  
|<span data-ttu-id="89f14-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="89f14-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="89f14-386">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-386">Int64</span></span>|  
|<span data-ttu-id="89f14-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="89f14-388">String</span><span class="sxs-lookup"><span data-stu-id="89f14-388">String</span></span>|  
|<span data-ttu-id="89f14-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="89f14-390">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-390">String</span></span>|  
|<span data-ttu-id="89f14-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="89f14-392">String</span><span class="sxs-lookup"><span data-stu-id="89f14-392">String</span></span>|  
|<span data-ttu-id="89f14-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="89f14-394">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-394">String</span></span>|  
|<span data-ttu-id="89f14-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="89f14-396">String</span><span class="sxs-lookup"><span data-stu-id="89f14-396">String</span></span>|  
|<span data-ttu-id="89f14-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-397">COLLATION_NAME</span></span>|<span data-ttu-id="89f14-398">String</span><span class="sxs-lookup"><span data-stu-id="89f14-398">String</span></span>|  
|<span data-ttu-id="89f14-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="89f14-400">String</span><span class="sxs-lookup"><span data-stu-id="89f14-400">String</span></span>|  
|<span data-ttu-id="89f14-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="89f14-402">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-402">String</span></span>|  
|<span data-ttu-id="89f14-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-403">DOMAIN_NAME</span></span>|<span data-ttu-id="89f14-404">String</span><span class="sxs-lookup"><span data-stu-id="89f14-404">String</span></span>|  
|<span data-ttu-id="89f14-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89f14-405">DESCRIPTION</span></span>|<span data-ttu-id="89f14-406">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="89f14-407">절차</span><span class="sxs-lookup"><span data-stu-id="89f14-407">Procedures</span></span>  
  
|<span data-ttu-id="89f14-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="89f14-408">ColumnName</span></span>|<span data-ttu-id="89f14-409">DataType</span><span class="sxs-lookup"><span data-stu-id="89f14-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="89f14-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="89f14-411">String</span><span class="sxs-lookup"><span data-stu-id="89f14-411">String</span></span>|  
|<span data-ttu-id="89f14-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="89f14-413">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-413">String</span></span>|  
|<span data-ttu-id="89f14-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="89f14-415">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-415">String</span></span>|  
|<span data-ttu-id="89f14-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="89f14-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="89f14-417">Int16</span><span class="sxs-lookup"><span data-stu-id="89f14-417">Int16</span></span>|  
|<span data-ttu-id="89f14-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="89f14-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="89f14-419">String</span><span class="sxs-lookup"><span data-stu-id="89f14-419">String</span></span>|  
|<span data-ttu-id="89f14-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89f14-420">DESCRIPTION</span></span>|<span data-ttu-id="89f14-421">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-421">String</span></span>|  
|<span data-ttu-id="89f14-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="89f14-422">DATE_CREATED</span></span>|<span data-ttu-id="89f14-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="89f14-423">DateTime</span></span>|  
|<span data-ttu-id="89f14-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="89f14-424">DATE_MODIFIED</span></span>|<span data-ttu-id="89f14-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="89f14-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="89f14-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="89f14-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="89f14-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="89f14-427">ColumnName</span></span>|<span data-ttu-id="89f14-428">DataType</span><span class="sxs-lookup"><span data-stu-id="89f14-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="89f14-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="89f14-430">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-430">String</span></span>|  
|<span data-ttu-id="89f14-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="89f14-432">String</span><span class="sxs-lookup"><span data-stu-id="89f14-432">String</span></span>|  
|<span data-ttu-id="89f14-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="89f14-434">String</span><span class="sxs-lookup"><span data-stu-id="89f14-434">String</span></span>|  
|<span data-ttu-id="89f14-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-435">COLUMN_NAME</span></span>|<span data-ttu-id="89f14-436">String</span><span class="sxs-lookup"><span data-stu-id="89f14-436">String</span></span>|  
|<span data-ttu-id="89f14-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="89f14-437">COLUMN_GUID</span></span>|<span data-ttu-id="89f14-438">Guid</span><span class="sxs-lookup"><span data-stu-id="89f14-438">Guid</span></span>|  
|<span data-ttu-id="89f14-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="89f14-439">COLUMN_PROPID</span></span>|<span data-ttu-id="89f14-440">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-440">Int64</span></span>|  
|<span data-ttu-id="89f14-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="89f14-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="89f14-442">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-442">Int64</span></span>|  
|<span data-ttu-id="89f14-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="89f14-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="89f14-444">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-444">Int64</span></span>|  
|<span data-ttu-id="89f14-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="89f14-445">IS_NULLABLE</span></span>|<span data-ttu-id="89f14-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-446">Boolean</span></span>|  
|<span data-ttu-id="89f14-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="89f14-447">DATA_TYPE</span></span>|<span data-ttu-id="89f14-448">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-448">Int32</span></span>|  
|<span data-ttu-id="89f14-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="89f14-449">TYPE_GUID</span></span>|<span data-ttu-id="89f14-450">Guid</span><span class="sxs-lookup"><span data-stu-id="89f14-450">Guid</span></span>|  
|<span data-ttu-id="89f14-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="89f14-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="89f14-452">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-452">Int64</span></span>|  
|<span data-ttu-id="89f14-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="89f14-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="89f14-454">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-454">Int64</span></span>|  
|<span data-ttu-id="89f14-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="89f14-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="89f14-456">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-456">Int32</span></span>|  
|<span data-ttu-id="89f14-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="89f14-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="89f14-458">Int16</span><span class="sxs-lookup"><span data-stu-id="89f14-458">Int16</span></span>|  
|<span data-ttu-id="89f14-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89f14-459">DESCRIPTION</span></span>|<span data-ttu-id="89f14-460">String</span><span class="sxs-lookup"><span data-stu-id="89f14-460">String</span></span>|  
|<span data-ttu-id="89f14-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="89f14-461">OVERLOAD</span></span>|<span data-ttu-id="89f14-462">Int16</span><span class="sxs-lookup"><span data-stu-id="89f14-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="89f14-463">뷰</span><span class="sxs-lookup"><span data-stu-id="89f14-463">Views</span></span>  
  
|<span data-ttu-id="89f14-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="89f14-464">ColumnName</span></span>|<span data-ttu-id="89f14-465">DataType</span><span class="sxs-lookup"><span data-stu-id="89f14-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="89f14-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-466">TABLE_CATALOG</span></span>|<span data-ttu-id="89f14-467">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-467">String</span></span>|  
|<span data-ttu-id="89f14-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="89f14-469">String</span><span class="sxs-lookup"><span data-stu-id="89f14-469">String</span></span>|  
|<span data-ttu-id="89f14-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-470">TABLE_NAME</span></span>|<span data-ttu-id="89f14-471">String</span><span class="sxs-lookup"><span data-stu-id="89f14-471">String</span></span>|  
|<span data-ttu-id="89f14-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="89f14-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="89f14-473">String</span><span class="sxs-lookup"><span data-stu-id="89f14-473">String</span></span>|  
|<span data-ttu-id="89f14-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="89f14-474">CHECK_OPTION</span></span>|<span data-ttu-id="89f14-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-475">Boolean</span></span>|  
|<span data-ttu-id="89f14-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="89f14-476">IS_UPDATABLE</span></span>|<span data-ttu-id="89f14-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-477">Boolean</span></span>|  
|<span data-ttu-id="89f14-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89f14-478">DESCRIPTION</span></span>|<span data-ttu-id="89f14-479">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-479">String</span></span>|  
|<span data-ttu-id="89f14-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="89f14-480">DATE_CREATED</span></span>|<span data-ttu-id="89f14-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="89f14-481">DateTime</span></span>|  
|<span data-ttu-id="89f14-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="89f14-482">DATE_MODIFIED</span></span>|<span data-ttu-id="89f14-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="89f14-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="89f14-484">인덱스</span><span class="sxs-lookup"><span data-stu-id="89f14-484">Indexes</span></span>  
  
|<span data-ttu-id="89f14-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="89f14-485">ColumnName</span></span>|<span data-ttu-id="89f14-486">DataType</span><span class="sxs-lookup"><span data-stu-id="89f14-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="89f14-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-487">TABLE_CATALOG</span></span>|<span data-ttu-id="89f14-488">String</span><span class="sxs-lookup"><span data-stu-id="89f14-488">String</span></span>|  
|<span data-ttu-id="89f14-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="89f14-490">String</span><span class="sxs-lookup"><span data-stu-id="89f14-490">String</span></span>|  
|<span data-ttu-id="89f14-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-491">TABLE_NAME</span></span>|<span data-ttu-id="89f14-492">String</span><span class="sxs-lookup"><span data-stu-id="89f14-492">String</span></span>|  
|<span data-ttu-id="89f14-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-493">INDEX_CATALOG</span></span>|<span data-ttu-id="89f14-494">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-494">String</span></span>|  
|<span data-ttu-id="89f14-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="89f14-496">String</span><span class="sxs-lookup"><span data-stu-id="89f14-496">String</span></span>|  
|<span data-ttu-id="89f14-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-497">INDEX_NAME</span></span>|<span data-ttu-id="89f14-498">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-498">String</span></span>|  
|<span data-ttu-id="89f14-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="89f14-499">PRIMARY_KEY</span></span>|<span data-ttu-id="89f14-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-500">Boolean</span></span>|  
|<span data-ttu-id="89f14-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="89f14-501">UNIQUE</span></span>|<span data-ttu-id="89f14-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-502">Boolean</span></span>|  
|<span data-ttu-id="89f14-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="89f14-503">CLUSTERED</span></span>|<span data-ttu-id="89f14-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-504">Boolean</span></span>|  
|<span data-ttu-id="89f14-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="89f14-505">TYPE</span></span>|<span data-ttu-id="89f14-506">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-506">Int32</span></span>|  
|<span data-ttu-id="89f14-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="89f14-507">FILL_FACTOR</span></span>|<span data-ttu-id="89f14-508">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-508">Int32</span></span>|  
|<span data-ttu-id="89f14-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="89f14-509">INITIAL_SIZE</span></span>|<span data-ttu-id="89f14-510">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-510">Int32</span></span>|  
|<span data-ttu-id="89f14-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="89f14-511">NULLS</span></span>|<span data-ttu-id="89f14-512">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-512">Int32</span></span>|  
|<span data-ttu-id="89f14-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="89f14-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="89f14-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-514">Boolean</span></span>|  
|<span data-ttu-id="89f14-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="89f14-515">AUTO_UPDATE</span></span>|<span data-ttu-id="89f14-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-516">Boolean</span></span>|  
|<span data-ttu-id="89f14-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="89f14-517">NULL_COLLATION</span></span>|<span data-ttu-id="89f14-518">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-518">Int32</span></span>|  
|<span data-ttu-id="89f14-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="89f14-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="89f14-520">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-520">Int64</span></span>|  
|<span data-ttu-id="89f14-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-521">COLUMN_NAME</span></span>|<span data-ttu-id="89f14-522">String</span><span class="sxs-lookup"><span data-stu-id="89f14-522">String</span></span>|  
|<span data-ttu-id="89f14-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="89f14-523">COLUMN_GUID</span></span>|<span data-ttu-id="89f14-524">Guid</span><span class="sxs-lookup"><span data-stu-id="89f14-524">Guid</span></span>|  
|<span data-ttu-id="89f14-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="89f14-525">COLUMN_PROPID</span></span>|<span data-ttu-id="89f14-526">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-526">Int64</span></span>|  
|<span data-ttu-id="89f14-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="89f14-527">COLLATION</span></span>|<span data-ttu-id="89f14-528">Int16</span><span class="sxs-lookup"><span data-stu-id="89f14-528">Int16</span></span>|  
|<span data-ttu-id="89f14-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="89f14-529">CARDINALITY</span></span>|<span data-ttu-id="89f14-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="89f14-530">Decimal</span></span>|  
|<span data-ttu-id="89f14-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="89f14-531">PAGES</span></span>|<span data-ttu-id="89f14-532">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-532">Int32</span></span>|  
|<span data-ttu-id="89f14-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="89f14-533">FILTER_CONDITION</span></span>|<span data-ttu-id="89f14-534">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-534">String</span></span>|  
|<span data-ttu-id="89f14-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="89f14-535">INTEGRATED</span></span>|<span data-ttu-id="89f14-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="89f14-537">Microsoft Jet OLE DB</span><span class="sxs-lookup"><span data-stu-id="89f14-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="89f14-538">Microsoft Jet OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="89f14-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="89f14-539">테이블</span><span class="sxs-lookup"><span data-stu-id="89f14-539">Tables</span></span>  
  
- <span data-ttu-id="89f14-540">열</span><span class="sxs-lookup"><span data-stu-id="89f14-540">Columns</span></span>  
  
- <span data-ttu-id="89f14-541">절차</span><span class="sxs-lookup"><span data-stu-id="89f14-541">Procedures</span></span>  
  
- <span data-ttu-id="89f14-542">뷰</span><span class="sxs-lookup"><span data-stu-id="89f14-542">Views</span></span>  
  
- <span data-ttu-id="89f14-543">인덱스</span><span class="sxs-lookup"><span data-stu-id="89f14-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="89f14-544">테이블</span><span class="sxs-lookup"><span data-stu-id="89f14-544">Tables</span></span>  
  
|<span data-ttu-id="89f14-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="89f14-545">ColumnName</span></span>|<span data-ttu-id="89f14-546">DataType</span><span class="sxs-lookup"><span data-stu-id="89f14-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="89f14-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-547">TABLE_CATALOG</span></span>|<span data-ttu-id="89f14-548">String</span><span class="sxs-lookup"><span data-stu-id="89f14-548">String</span></span>|  
|<span data-ttu-id="89f14-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="89f14-550">String</span><span class="sxs-lookup"><span data-stu-id="89f14-550">String</span></span>|  
|<span data-ttu-id="89f14-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-551">TABLE_NAME</span></span>|<span data-ttu-id="89f14-552">String</span><span class="sxs-lookup"><span data-stu-id="89f14-552">String</span></span>|  
|<span data-ttu-id="89f14-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="89f14-553">TABLE_TYPE</span></span>|<span data-ttu-id="89f14-554">String</span><span class="sxs-lookup"><span data-stu-id="89f14-554">String</span></span>|  
|<span data-ttu-id="89f14-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="89f14-555">TABLE_GUID</span></span>|<span data-ttu-id="89f14-556">Guid</span><span class="sxs-lookup"><span data-stu-id="89f14-556">Guid</span></span>|  
|<span data-ttu-id="89f14-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89f14-557">DESCRIPTION</span></span>|<span data-ttu-id="89f14-558">String</span><span class="sxs-lookup"><span data-stu-id="89f14-558">String</span></span>|  
|<span data-ttu-id="89f14-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="89f14-559">TABLE_PROPID</span></span>|<span data-ttu-id="89f14-560">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-560">Int64</span></span>|  
|<span data-ttu-id="89f14-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="89f14-561">DATE_CREATED</span></span>|<span data-ttu-id="89f14-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="89f14-562">DateTime</span></span>|  
|<span data-ttu-id="89f14-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="89f14-563">DATE_MODIFIED</span></span>|<span data-ttu-id="89f14-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="89f14-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="89f14-565">열</span><span class="sxs-lookup"><span data-stu-id="89f14-565">Columns</span></span>  
  
|<span data-ttu-id="89f14-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="89f14-566">ColumnName</span></span>|<span data-ttu-id="89f14-567">DataType</span><span class="sxs-lookup"><span data-stu-id="89f14-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="89f14-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-568">TABLE_CATALOG</span></span>|<span data-ttu-id="89f14-569">String</span><span class="sxs-lookup"><span data-stu-id="89f14-569">String</span></span>|  
|<span data-ttu-id="89f14-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="89f14-571">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-571">String</span></span>|  
|<span data-ttu-id="89f14-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-572">TABLE_NAME</span></span>|<span data-ttu-id="89f14-573">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-573">String</span></span>|  
|<span data-ttu-id="89f14-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-574">COLUMN_NAME</span></span>|<span data-ttu-id="89f14-575">String</span><span class="sxs-lookup"><span data-stu-id="89f14-575">String</span></span>|  
|<span data-ttu-id="89f14-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="89f14-576">COLUMN_GUID</span></span>|<span data-ttu-id="89f14-577">Guid</span><span class="sxs-lookup"><span data-stu-id="89f14-577">Guid</span></span>|  
|<span data-ttu-id="89f14-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="89f14-578">COLUMN_PROPID</span></span>|<span data-ttu-id="89f14-579">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-579">Int64</span></span>|  
|<span data-ttu-id="89f14-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="89f14-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="89f14-581">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-581">Int64</span></span>|  
|<span data-ttu-id="89f14-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="89f14-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="89f14-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-583">Boolean</span></span>|  
|<span data-ttu-id="89f14-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="89f14-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="89f14-585">String</span><span class="sxs-lookup"><span data-stu-id="89f14-585">String</span></span>|  
|<span data-ttu-id="89f14-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="89f14-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="89f14-587">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-587">Int64</span></span>|  
|<span data-ttu-id="89f14-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="89f14-588">IS_NULLABLE</span></span>|<span data-ttu-id="89f14-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-589">Boolean</span></span>|  
|<span data-ttu-id="89f14-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="89f14-590">DATA_TYPE</span></span>|<span data-ttu-id="89f14-591">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-591">Int32</span></span>|  
|<span data-ttu-id="89f14-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="89f14-592">TYPE_GUID</span></span>|<span data-ttu-id="89f14-593">Guid</span><span class="sxs-lookup"><span data-stu-id="89f14-593">Guid</span></span>|  
|<span data-ttu-id="89f14-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="89f14-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="89f14-595">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-595">Int64</span></span>|  
|<span data-ttu-id="89f14-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="89f14-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="89f14-597">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-597">Int64</span></span>|  
|<span data-ttu-id="89f14-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="89f14-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="89f14-599">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-599">Int32</span></span>|  
|<span data-ttu-id="89f14-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="89f14-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="89f14-601">Int16</span><span class="sxs-lookup"><span data-stu-id="89f14-601">Int16</span></span>|  
|<span data-ttu-id="89f14-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="89f14-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="89f14-603">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-603">Int64</span></span>|  
|<span data-ttu-id="89f14-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="89f14-605">String</span><span class="sxs-lookup"><span data-stu-id="89f14-605">String</span></span>|  
|<span data-ttu-id="89f14-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="89f14-607">String</span><span class="sxs-lookup"><span data-stu-id="89f14-607">String</span></span>|  
|<span data-ttu-id="89f14-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="89f14-609">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-609">String</span></span>|  
|<span data-ttu-id="89f14-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="89f14-611">String</span><span class="sxs-lookup"><span data-stu-id="89f14-611">String</span></span>|  
|<span data-ttu-id="89f14-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="89f14-613">String</span><span class="sxs-lookup"><span data-stu-id="89f14-613">String</span></span>|  
|<span data-ttu-id="89f14-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-614">COLLATION_NAME</span></span>|<span data-ttu-id="89f14-615">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-615">String</span></span>|  
|<span data-ttu-id="89f14-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="89f14-617">String</span><span class="sxs-lookup"><span data-stu-id="89f14-617">String</span></span>|  
|<span data-ttu-id="89f14-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="89f14-619">String</span><span class="sxs-lookup"><span data-stu-id="89f14-619">String</span></span>|  
|<span data-ttu-id="89f14-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-620">DOMAIN_NAME</span></span>|<span data-ttu-id="89f14-621">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-621">String</span></span>|  
|<span data-ttu-id="89f14-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89f14-622">DESCRIPTION</span></span>|<span data-ttu-id="89f14-623">String</span><span class="sxs-lookup"><span data-stu-id="89f14-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="89f14-624">절차</span><span class="sxs-lookup"><span data-stu-id="89f14-624">Procedures</span></span>  
  
|<span data-ttu-id="89f14-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="89f14-625">ColumnName</span></span>|<span data-ttu-id="89f14-626">DataType</span><span class="sxs-lookup"><span data-stu-id="89f14-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="89f14-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="89f14-628">String</span><span class="sxs-lookup"><span data-stu-id="89f14-628">String</span></span>|  
|<span data-ttu-id="89f14-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="89f14-630">String</span><span class="sxs-lookup"><span data-stu-id="89f14-630">String</span></span>|  
|<span data-ttu-id="89f14-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="89f14-632">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-632">String</span></span>|  
|<span data-ttu-id="89f14-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="89f14-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="89f14-634">Int16</span><span class="sxs-lookup"><span data-stu-id="89f14-634">Int16</span></span>|  
|<span data-ttu-id="89f14-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="89f14-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="89f14-636">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-636">String</span></span>|  
|<span data-ttu-id="89f14-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89f14-637">DESCRIPTION</span></span>|<span data-ttu-id="89f14-638">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-638">String</span></span>|  
|<span data-ttu-id="89f14-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="89f14-639">DATE_CREATED</span></span>|<span data-ttu-id="89f14-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="89f14-640">DateTime</span></span>|  
|<span data-ttu-id="89f14-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="89f14-641">DATE_MODIFIED</span></span>|<span data-ttu-id="89f14-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="89f14-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="89f14-643">뷰</span><span class="sxs-lookup"><span data-stu-id="89f14-643">Views</span></span>  
  
|<span data-ttu-id="89f14-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="89f14-644">ColumnName</span></span>|<span data-ttu-id="89f14-645">DataType</span><span class="sxs-lookup"><span data-stu-id="89f14-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="89f14-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-646">TABLE_CATALOG</span></span>|<span data-ttu-id="89f14-647">String</span><span class="sxs-lookup"><span data-stu-id="89f14-647">String</span></span>|  
|<span data-ttu-id="89f14-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="89f14-649">String</span><span class="sxs-lookup"><span data-stu-id="89f14-649">String</span></span>|  
|<span data-ttu-id="89f14-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-650">TABLE_NAME</span></span>|<span data-ttu-id="89f14-651">String</span><span class="sxs-lookup"><span data-stu-id="89f14-651">String</span></span>|  
|<span data-ttu-id="89f14-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="89f14-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="89f14-653">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-653">String</span></span>|  
|<span data-ttu-id="89f14-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="89f14-654">CHECK_OPTION</span></span>|<span data-ttu-id="89f14-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-655">Boolean</span></span>|  
|<span data-ttu-id="89f14-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="89f14-656">IS_UPDATABLE</span></span>|<span data-ttu-id="89f14-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-657">Boolean</span></span>|  
|<span data-ttu-id="89f14-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="89f14-658">DESCRIPTION</span></span>|<span data-ttu-id="89f14-659">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-659">String</span></span>|  
|<span data-ttu-id="89f14-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="89f14-660">DATE_CREATED</span></span>|<span data-ttu-id="89f14-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="89f14-661">DateTime</span></span>|  
|<span data-ttu-id="89f14-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="89f14-662">DATE_MODIFIED</span></span>|<span data-ttu-id="89f14-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="89f14-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="89f14-664">인덱스</span><span class="sxs-lookup"><span data-stu-id="89f14-664">Indexes</span></span>  
  
|<span data-ttu-id="89f14-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="89f14-665">ColumnName</span></span>|<span data-ttu-id="89f14-666">DataType</span><span class="sxs-lookup"><span data-stu-id="89f14-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="89f14-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-667">TABLE_CATALOG</span></span>|<span data-ttu-id="89f14-668">String</span><span class="sxs-lookup"><span data-stu-id="89f14-668">String</span></span>|  
|<span data-ttu-id="89f14-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="89f14-670">String</span><span class="sxs-lookup"><span data-stu-id="89f14-670">String</span></span>|  
|<span data-ttu-id="89f14-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-671">TABLE_NAME</span></span>|<span data-ttu-id="89f14-672">String</span><span class="sxs-lookup"><span data-stu-id="89f14-672">String</span></span>|  
|<span data-ttu-id="89f14-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="89f14-673">INDEX_CATALOG</span></span>|<span data-ttu-id="89f14-674">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-674">String</span></span>|  
|<span data-ttu-id="89f14-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="89f14-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="89f14-676">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-676">String</span></span>|  
|<span data-ttu-id="89f14-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-677">INDEX_NAME</span></span>|<span data-ttu-id="89f14-678">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-678">String</span></span>|  
|<span data-ttu-id="89f14-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="89f14-679">PRIMARY_KEY</span></span>|<span data-ttu-id="89f14-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-680">Boolean</span></span>|  
|<span data-ttu-id="89f14-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="89f14-681">UNIQUE</span></span>|<span data-ttu-id="89f14-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-682">Boolean</span></span>|  
|<span data-ttu-id="89f14-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="89f14-683">CLUSTERED</span></span>|<span data-ttu-id="89f14-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-684">Boolean</span></span>|  
|<span data-ttu-id="89f14-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="89f14-685">TYPE</span></span>|<span data-ttu-id="89f14-686">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-686">Int32</span></span>|  
|<span data-ttu-id="89f14-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="89f14-687">FILL_FACTOR</span></span>|<span data-ttu-id="89f14-688">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-688">Int32</span></span>|  
|<span data-ttu-id="89f14-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="89f14-689">INITIAL_SIZE</span></span>|<span data-ttu-id="89f14-690">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-690">Int32</span></span>|  
|<span data-ttu-id="89f14-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="89f14-691">NULLS</span></span>|<span data-ttu-id="89f14-692">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-692">Int32</span></span>|  
|<span data-ttu-id="89f14-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="89f14-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="89f14-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-694">Boolean</span></span>|  
|<span data-ttu-id="89f14-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="89f14-695">AUTO_UPDATE</span></span>|<span data-ttu-id="89f14-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-696">Boolean</span></span>|  
|<span data-ttu-id="89f14-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="89f14-697">NULL_COLLATION</span></span>|<span data-ttu-id="89f14-698">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-698">Int32</span></span>|  
|<span data-ttu-id="89f14-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="89f14-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="89f14-700">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-700">Int64</span></span>|  
|<span data-ttu-id="89f14-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="89f14-701">COLUMN_NAME</span></span>|<span data-ttu-id="89f14-702">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-702">String</span></span>|  
|<span data-ttu-id="89f14-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="89f14-703">COLUMN_GUID</span></span>|<span data-ttu-id="89f14-704">Guid</span><span class="sxs-lookup"><span data-stu-id="89f14-704">Guid</span></span>|  
|<span data-ttu-id="89f14-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="89f14-705">COLUMN_PROPID</span></span>|<span data-ttu-id="89f14-706">Int64</span><span class="sxs-lookup"><span data-stu-id="89f14-706">Int64</span></span>|  
|<span data-ttu-id="89f14-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="89f14-707">COLLATION</span></span>|<span data-ttu-id="89f14-708">Int16</span><span class="sxs-lookup"><span data-stu-id="89f14-708">Int16</span></span>|  
|<span data-ttu-id="89f14-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="89f14-709">CARDINALITY</span></span>|<span data-ttu-id="89f14-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="89f14-710">Decimal</span></span>|  
|<span data-ttu-id="89f14-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="89f14-711">PAGES</span></span>|<span data-ttu-id="89f14-712">Int32</span><span class="sxs-lookup"><span data-stu-id="89f14-712">Int32</span></span>|  
|<span data-ttu-id="89f14-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="89f14-713">FILTER_CONDITION</span></span>|<span data-ttu-id="89f14-714">문자열</span><span class="sxs-lookup"><span data-stu-id="89f14-714">String</span></span>|  
|<span data-ttu-id="89f14-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="89f14-715">INTEGRATED</span></span>|<span data-ttu-id="89f14-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="89f14-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89f14-717">참고자료</span><span class="sxs-lookup"><span data-stu-id="89f14-717">See also</span></span>

- [<span data-ttu-id="89f14-718">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="89f14-718">ADO.NET Overview</span></span>](ado-net-overview.md)
