public void clearStack() {
    //Here we are clearing back stack fragment entries
    int backStackEntry = getSupportFragmentManager().getBackStackEntryCount();
    if (backStackEntry > 0) {
        for (int i = 0; i < backStackEntry; i++) {
            getSupportFragmentManager().popBackStackImmediate();
        }
    }

    //Here we are removing all the fragment that are shown here
    if (getSupportFragmentManager().getFragments() != null && getSupportFragmentManager().getFragments().size() > 0) {
        for (int i = 0; i < getSupportFragmentManager().getFragments().size(); i++) {
            Fragment mFragment = getSupportFragmentManager().getFragments().get(i);
            if (mFragment != null) {
                getSupportFragmentManager().beginTransaction().remove(mFragment).commit();
            }
        }
    }
}
