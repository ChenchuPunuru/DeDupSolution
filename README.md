# DeDupSolution
package com.Solutions;

import java.util.ArrayList;
import java.util.HashSet;
import java.util.Iterator;
import java.util.LinkedHashSet;
import java.util.List;
import java.util.Set;
import java.util.TreeSet;

public class DeDup {

	public int[] randomIntegers = { 1, 2, 34, 34, 25, 1, 45, 3, 26, 85, 4, 34,
			86, 25, 43, 2, 1, 10000, 11, 16, 19, 1, 18, 4, 9, 3, 20, 17, 8, 15,
			6, 2, 5, 10, 14, 12, 13, 7, 8, 9, 1, 2, 15, 12, 18, 10, 14, 20, 17,
			16, 3, 6, 19, 13, 5, 11, 4, 7, 19, 16, 5, 9, 12, 3, 20, 7, 15, 17,
			10, 6, 1, 8, 18, 4, 14, 13, 2, 11 };

	private int[] removeDuplicates(int[] arr) throws Exception {
		int arrSize = arr.length;
		try {

			for (int i = 0; i < arrSize; i++) {
				for (int j = i + 1; j < arrSize; j++) {
					if (arr[i] == arr[j]) {
						int shiftLeft = j;
						for (int k = j + 1; k < arrSize; k++, shiftLeft++) {
							arr[shiftLeft] = arr[k];
						}
						arrSize--;
						j--;
					}
				}

			}

			int[] afterDuplicates = new int[arrSize];
			for (int i = 0; i < arrSize; i++) {
				afterDuplicates[i] = arr[i];
			}
			return afterDuplicates;
		} catch (Exception e) {
			System.out.println(" Exception in removeDuplicates Method"
					+ e.getMessage());
			throw e;
		}

	}

	/**
	 * convert integer List to Maintain Insertion Order
	 * 
	 * @param List
	 *            <Integer>
	 * @return Set<Integer>
	 */

	private Set<Integer> removeDuplicatesAndMaintainInsertOrder(
			List<Integer> listWithDuplicates) throws Exception {
		try {
			Set<Integer> resultSet = new LinkedHashSet<Integer>(
					listWithDuplicates);
			return resultSet;
		} catch (Exception e) {
			throw e;
		}
	}

	/**
	 * convert integer List to a Set
	 * 
	 * @param List
	 *            <Integer> []
	 * @return Set<Integer>
	 */
	private Set<Integer> removeDuplicatesUsingSet(List<Integer> inputList)
			throws Exception {
		try {
			Set<Integer> set = new HashSet<Integer>(inputList);
			return set;
		} catch (Exception e) {
			System.out.println(" Exception in removeDuplicatesUsingSet Method"
					+ e.getMessage());
			throw e;
		}
	}

	/**
	 * convert integer List to TreeSet to maintain Ascending Order
	 * 
	 * @param List
	 *            <Integer> []
	 * @return Set<Integer>
	 */
	private TreeSet<Integer> sortedOrder(List<Integer> inputList)
			throws Exception {
		try {
			TreeSet<Integer> ascenOrder = new TreeSet<Integer>(inputList);
			return ascenOrder;
		} catch (Exception e) {
			System.out.println(" Exception in sortedOrder Method"
					+ e.getMessage());
			throw e;
		}

	}

	/**
	 * convert integer Array to a List
	 * 
	 * @param int []
	 * @return List<Integer>
	 */
	private List<Integer> convertArrayToList(int[] randomIntegers) {
		List<Integer> integersAsList = new ArrayList<Integer>();
		for (int element : randomIntegers) {
			integersAsList.add(element);
		}
		return integersAsList;
	}

	public static void main(String[] args) {
		DeDup deDup = new DeDup();
		try {

			int[] removeDuplicates = deDup
					.removeDuplicates(deDup.randomIntegers);
			List<Integer> listValue = deDup
					.convertArrayToList(deDup.randomIntegers);
			Set<Integer> resultValueUsingSet = deDup
					.removeDuplicatesUsingSet(listValue);

			Set<Integer> resultValueMainInsertOrder = deDup
					.removeDuplicatesAndMaintainInsertOrder(listValue);
			TreeSet<Integer> ascenOrder = deDup.sortedOrder(listValue);

		} catch (Exception e) {
			System.out.println(" Exception in Main class" + e.getMessage());
		}
	}

}
