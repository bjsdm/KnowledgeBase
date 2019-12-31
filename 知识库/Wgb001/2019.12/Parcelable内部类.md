问题 ：写一个子类Parcelable到另一个包裹(Write a sub class of Parcelable to another Parcel)


class A implements Parcelable {

}


class B implements Parcelable{

    public void writeToParcel(Parcel dest, int flags) {
        dest.write ??? 
    }
}

解决方式：


class B implements Parcelable{
//lets assume you have A as a data member 

A obj;
public void writeToParcel(Parcel dest, int flags) {

        dest.writeParcelable(obj , flags);

    }
}



obj = (A)in.readParcelable(A.class.getClassLoader());

