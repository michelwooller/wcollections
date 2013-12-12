package com.wooller.collections.TwoValuesHashMap;

import java.util.HashMap;

/**
 * @author Michel Lucas Corrêa <michellucascorrea@gmail.com>
 * @version 1.0
 * @see HashMap
 * A map that implements a pair of values to the same key
 * @param <K> Class of key
 * @param <V1> Class of first value
 * @param <V2> Class of second value
 */
public class TwoValuesHashMap<K, V1, V2> extends HashMap<K, TwoValuesHashMap.TwoValues<V1, V2>> {

    /**
     * @param key Class of key
     * @param valueOne Class of first value
     * @param valueTwo Class of second value
     * @return return a instance of TwoValuesHashMap
     */
    public TwoValuesHashMap.TwoValues<V1, V2> put(K key, V1 valueOne, V2 valueTwo) {
        TwoValuesHashMap.TwoValues<V1, V2> newValue = new TwoValuesHashMap.TwoValues<V1, V2>(valueOne, valueTwo);
        return super.put(key, newValue);
    }

    /**
     * A special entry for TwoValuesHashMap
     * @param <K> Class of key
     * @param <V1> Class of first value
     * @param <V2> Class of second value
     */
    public static class TwoValuesEntry<K, V1, V2> implements Entry<K, TwoValues<V1, V2>> {
        private K key;
        private TwoValues<V1, V2> value;

        public K getKey() {
            return key;
        }

        public TwoValues<V1, V2> getValue() {
            return value;
        }

        public TwoValues<V1, V2> setValue(TwoValues<V1, V2> value) {
            TwoValues<V1, V2> oldValue = this.value;
            this.value = value;
            return oldValue;
        }
    }
    
    /**
     * A value object for internal use into TwoValuesHashMap
     * @param <V1>
     * @param <V2>
     */
    public static class TwoValues<V1, V2> {
        private V1 valueOne;
        private V2 valueTwo;

        public TwoValues() {
            this(null, null);
        }

        public TwoValues(V1 valueOne, V2 valueTwo) {
            this.valueOne = valueOne;
            this.valueTwo = valueTwo;
        }

        public void setValueOne(V1 valueOne) {
            this.valueOne = valueOne;
        }

        public V1 getValueOne() {
            return valueOne;
        }

        public void setValueTwo(V2 valueTwo) {
            this.valueTwo = valueTwo;
        }

        public V2 getValueTwo() {
            return valueTwo;
        }


        @Override
        public boolean equals(Object object) {
            if (this == object) {
                return true;
            }
            if (!(object instanceof TwoValuesHashMap.TwoValues)) {
                return false;
            }

            final TwoValuesHashMap.TwoValues other = (TwoValuesHashMap.TwoValues)object;
            if (getValueOne() == null ? other.getValueOne() != null : !getValueOne().equals(other.getValueOne())) {
                return false;
            }

            if (getValueTwo() == null ? other.getValueTwo() != null : !getValueTwo().equals(other.getValueTwo())) {
                return false;
            }
            return true;
        }

        @Override
        public int hashCode() {
            final int PRIME = 37;
            int result = 1;
            result = PRIME * result + ((getValueOne == null) ? 0 : getValueOne.hashCode());
            result = PRIME * result + ((getValueTwo == null) ? 0 : getValueTwo.hashCode());
            return result;
        }
    }
}
